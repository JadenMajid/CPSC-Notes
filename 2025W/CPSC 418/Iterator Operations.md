## Reduce
```erlang
reduce(WorkerTree, Leaf, Combine)-> Result.
```
- `WorkerTree` is a collection of worker processes organized as a tree(processes know who their parents and children are)
- `Leaf` is a function that is applied at leaves to produce a result to combine using reduce
- `Combine(Left, Right)` is a function applied at nodes
	- Should return same datatype as inputs
- `Result` is the value computed at the root of the tree

### Example

#### Count 3s
```erlang
count3s(WorkerTree, Key) ->
  wtree:reduce(WorkerTree,
    fun(ProcState) -> count3s_leaf(ProcState, Key) end,   % Leaf function
    fun(Left, Right) -> count3s_combine(Left, Right) end  % Combine function}
  ).

count3s_leaf(ProcState, Key) ->
  MyList = wtree:get(ProcState, Key), % fetch my part of the list from ProcState
  length([E || E <- MyList, E =:= 3]).  % select the 3s and return the length of that list

count3s_combine(Left, Right) -> Left+Right.
```
![[Screenshot 2026-01-14 at 15.30.12.png]]

