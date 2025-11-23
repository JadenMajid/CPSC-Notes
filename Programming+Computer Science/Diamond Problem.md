---
tags:
  - Coding
---
The diamond problem is a problem in [[Object Orientation]] that occurs when trying to have some object inherit from two different super classes. In the below case, if $B$ and $C$ both override methods in $A$, it is ambiguous which method it should inherit. The diamond problem can be sidestepped with an [[Interface]], which allows for multiple inheritance.
```
    A
   / \
  B   C
   \ /
    D   <-- ambiguity: which A method?
```