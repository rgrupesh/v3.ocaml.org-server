---
title: Determine the prime factors of a given positive integer (2)
number: "36"
difficulty: intermediate
tags: [ "arithmetic" ]
---

# Solution

```ocaml
# let factors n =
    let rec aux d n =
      if n = 1 then [] else
        if n mod d = 0 then
          match aux d (n / d) with
          | (h, n) :: t when h = d -> (h, n + 1) :: t
          | l -> (d, 1) :: l
        else aux (d + 1) n
    in
      aux 2 n
val factors : int -> (int * int) list = <fun>
```

# Statement

Construct a list containing the prime factors and their multiplicity.
*Hint:* The problem is similar to problem 
[Run-length encoding of a list (direct solution)](#Runlengthencodingofalistdirectsolutionmedium).

```ocaml
# factors 315;;
- : (int * int) list = [(3, 2); (5, 1); (7, 1)]
```
