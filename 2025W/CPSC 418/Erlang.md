Function programming languages where variable values never change(avoids race conditions)
- Uses message passing for inter-process communication
	- communication between processes is with send and receive expressions
	- communication tends to be the dominant cost
- All variables are immutable
	- Loops violate referential transparency
	- Need to use recursion instead
- Errors are expected, but failure does not cascade
- Dynamically, Strongly typed language
	- `1 + "2"` will error

## Syntax
### Vocabulary
- Variables
	- Immutable
	- must begin with a lower case letter, or enclosed in single quotes
	- Examples
		- Var_ex`
		- `Var`
- Atoms
	- Must start with lower case letter or surrounded by `'...'`
	- Consume memory, so be sparing if abused
		- do NOT generate dynamically
		- Not garbage collected
- Tuples
	- written in form `{Elem1, Elem2}`
	- `Point = {4,5}. {X,Y} = Point.` 
		- `X = 4`
- Lists
	- Written in form `[Elem1, Elem2]`
	- Strings are lists
	- List Operations
		- Right associative(right to left)
		- Concatenating lists
			- `A ++ B`
		- Removing elements
			- `A -- B`
			- `[2,4,2] -- [2,4] =:= [2]`
		- Getting list Head
			- `[Head|Tail]`
			- `|` is the Cons operator
		- Comprehensions
			- `[2*N|| N <- [1,2,3] =:= [2,4,6]`
- Binary Syntax
	- `Color = 16#FF00AA. Pixel = <<Color:24>>. Pixel =:= <<240, 154, 41>>`
	- `<<R:8,G:8,B:8>> = <<Pixel:24>>. R =:= 255`

### Boolean Algebra

| Name             | Symbol    | Notes                        |
| ---------------- | --------- | ---------------------------- |
| Exact Equality   | =:=       | 5.0 =:= 5 -> false           |
| Inequality       | =/=       |                              |
| Equality         | ==        | 5.0 == 5 -> true             |
| Other Comparison | <,<=,>,=< | <= is NOT valid, must use =< |
#### Weirdness
```
number < atom < reference < fun < port < pid < tuple < list < bit string
```
- true and false are atoms


## Modules
Modules are packages of functions under a file
- Declaring a module
	- `-module(module_name)`
- Exporting a function
	- `-export([function1/Arity,function2/Arity])`
- Importing a module
	- `-import(module_name,[function1,function2])`
- Using a function from a module
	- `module_name:function_name(...)`
- Compiling a module
	- `-compile(export_all)`

## Functions
Functions have Arity, ie: `Add/3` and `Add/2` are two completely different functions that take 3 and 2 arguments respectively.
### Syntax
```erlang
function fn_name(Arg1,Arg2)
	if Arg1 == hi then
		print("%s", Arg1)
	else if Arg2 == hello then
		print("Arg2 was %s",Arg2)
	else 
		print("no match")
	end
```

### Pattern Matching
If statements can be avoided with pattern matching
```erlang
function(X)->Expression;
function(Y)->Expression;
function(_)->Expression.
```
#### Guards
```erlang
can_drive(Age) when Age >= 16, Age =< -> true;
can_drive(_) -> false;
```

## Typing
erlang is dynamically but strongly typed
### Builtin Guards

```
is_atom/1           is_binary/1         
is_bitstring/1      is_boolean/1        is_builtin/3        
is_float/1          is_function/1       is_function/2       
is_integer/1        is_list/1           is_number/1         
is_pid/1            is_port/1           is_record/2         
is_record/3         is_reference/1      is_tuple/1
```

## Recursion
Erlang doesn't support loops(because of variable immutability) so everything is done with recursion. Tail recursion is preferable because we don't need to keep as much in memory

| Recursion Type | Notes                                           | Performance                                                                                       |
| -------------- | ----------------------------------------------- | ------------------------------------------------------------------------------------------------- |
| Head           | Recursive call occurs before processing is done | Worse for the stack if deep because we have to store each iteration on the stack before recursing |
| Tail           | Recursive call occurs after processing is done  | Better if deep, because we use constant memory space                                              |

### Example
Getting the length of a list with head recursion
```erlang
len([])->0;
len([_|T])-> 1+len(T).
```

Tail recursion
```erlang
len(L)->len(0,L);
len(N, [])->N;
len(N, [_|T])-> len(N+1, T).
```

### Higher Order functions(Lambda)
Erlang supports anonymous functions(yay!)
### Important Builtins
- Map
	- `lists:map/2`
- Filter
	- 
- Fold
	- `lists:foldl/3`
	- `lists:foldr/3`
- Flatten
	- `flatten/1`

## Errors and Exceptions

### Runtime Errors
erlang crashes when it gets a runtime error, see [this page for more](https://learnyousomeerlang.com/errors-and-exceptions#not-so-fast)

### Exceptions
There are 3 types
- errors
	- end execution and return a stack trace
- throws
	- class of exceptions for cases that programmer is expected to handle
	- called with `throw`
	- try-catch
- exits
	- Internal Exits
		- called with `exit/1` and make the current process stop execution
		- similar to errors, but `exit/1` doesnt return stack trace
	- External Exits
		- called with `exit/2`
		- have to do with concurrency

### Try-Catch
```erlang
% TODO
```

## Messages
Parallelism is achieved with message passing between processes. 
- Message passing is async
	- Messages sit in mailbox until process goes into receive block
	- Not matched Messages sit in mailbox 


```erlang
% Sending
Pid ! Expr

% Receiving
receive
	Pattern1 -> Expr1;
	Pattern2 -> Expr2;
	% ...
end
```

### Message ordering
- Message ordering is not guaranteed
	- A: `B ! Msg1, B ! Msg2`  B Mailbox ordering: `[Msg2, Msg1]`

### "Server" behaviour
- Can receive more messages with a recursive call (Bad 😢)
	- This is a memory leak(according to CPSC 213)
	- stack frames accumulate until stack overflows
	- CPSC 213 way of thinking means we think of the stack growing with the size of the stack frame on every recursive call
- Can use tail call elimination
	-  Can add an accumulator, then allows us to overwrite the original stack frame
	- Means we use $O(1)$ memory for infinite recursive calls 😋