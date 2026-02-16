# HW3b Solutions (Q1: Hypercube Congestion)

## (a) Route from `[1,0,1,1]` to `[0,1,1,0]` (dimension routing)

- bit 0: `[1,0,1,1] -> [0,0,1,1]`
- bit 1: `[0,0,1,1] -> [0,1,1,1]`
- bit 2: `[0,1,1,1] -> [0,1,1,1]` (no change)
- bit 3: `[0,1,1,1] -> [0,1,1,0]`

## (b) Two simultaneous routes with no congestion (D=4)

Choose:
- Message 1: `Src1=[0,0,0,0]`, `Dst1=[1,0,0,0]`
- Message 2: `Src2=[0,1,0,0]`, `Dst2=[0,1,1,0]`

Step-by-step:
- bit 0:
  - M1: `[0,0,0,0] -> [1,0,0,0]`
  - M2: `[0,1,0,0] -> [0,1,0,0]`
- bit 1:
  - M1: `[1,0,0,0] -> [1,0,0,0]`
  - M2: `[0,1,0,0] -> [0,1,0,0]`
- bit 2:
  - M1: `[1,0,0,0] -> [1,0,0,0]`
  - M2: `[0,1,0,0] -> [0,1,1,0]`
- bit 3:
  - M1: `[1,0,0,0] -> [1,0,0,0]`
  - M2: `[0,1,1,0] -> [0,1,1,0]`

No shared link is used.

## (c) Two simultaneous routes with congestion (different from handout example, D=4)

Choose:
- Message 1: `Src1=[0,0,0,0]`, `Dst1=[1,1,0,0]`
- Message 2: `Src2=[1,0,0,0]`, `Dst2=[1,1,1,1]`

Step-by-step:
- bit 0:
  - M1: `[0,0,0,0] -> [1,0,0,0]`
  - M2: `[1,0,0,0] -> [1,0,0,0]`
- bit 1:
  - M1: `[1,0,0,0] -> [1,1,0,0]`
  - M2: `[1,0,0,0] -> [1,1,0,0]`
  - Congestion on link `{[1,0,0,0], 1}`
- bit 2:
  - M1: `[1,1,0,0] -> [1,1,0,0]`
  - M2: `[1,1,0,0] -> [1,1,1,0]`
- bit 3:
  - M1: `[1,1,0,0] -> [1,1,0,0]`
  - M2: `[1,1,1,0] -> [1,1,1,1]`

## (d) `congestion_0(D)` results for D=2,4,6,8,10

Measured values:

| D | MaxCongestion | MaxCongestedLinks |
|---|---:|---:|
| 2 | 1  | 4  |
| 4 | 2  | 8  |
| 6 | 4  | 16 |
| 8 | 8  | 32 |
| 10 | 16 | 64 |

These match:
- `MaxCongestion = (1/2) * 2^(D/2)`
- `MaxCongestedLinks = 2 * 2^(D/2)`

## (e) Code implementation request: `hw3b:link_counts/1`

Implemented in `hw3/src/hw3b.erl`.

Validation run (all matched):
- `hw3b_lib:congestion(D) =:= hw3b_lib:congestion_0(D)` for `D=2,4,6,8,10`.

## (f) One maximally congested link for D=8 and the 8 causing pairs

One max-congestion link is:
- `{[1,0,0,0,1,0,0,1], 3}`

The 8 `{Src,Dst}` pairs using that link are:
1. `{[0,0,0,0,1,0,0,1], [1,0,0,1,0,0,0,0]}`
2. `{[0,0,1,0,1,0,0,1], [1,0,0,1,0,0,1,0]}`
3. `{[0,1,0,0,1,0,0,1], [1,0,0,1,0,1,0,0]}`
4. `{[0,1,1,0,1,0,0,1], [1,0,0,1,0,1,1,0]}`
5. `{[1,0,0,0,1,0,0,1], [1,0,0,1,1,0,0,0]}`
6. `{[1,0,1,0,1,0,0,1], [1,0,0,1,1,0,1,0]}`
7. `{[1,1,0,0,1,0,0,1], [1,0,0,1,1,1,0,0]}`
8. `{[1,1,1,0,1,0,0,1], [1,0,0,1,1,1,1,0]}`

## (g) Proof idea for at least one link with `(1/2)*2^(D/2)` messages

Let `D=2m` and use transpose traffic, so each message is from `Src=L++R` to `Dst=R++L`, where `|L|=|R|=m`.

Consider routing step `K=m-1` and pick any link `{Node,K}` with:
- `Node[K] = L_(m-1)` and
- `Node[m-1] = R_(m-1)` such that `L_(m-1) != R_(m-1)`

For a message to traverse `{Node,K}`, all bits of `R` are fixed by `Node` and `L_(m-1)` is fixed by `Node`, while bits `L_0..L_(m-2)` are free.
That gives exactly `2^(m-1)` messages mapped to that same link.
Because `L_(m-1) != R_(m-1)`, each such message actually crosses the link at step `K`.
Hence that link carries `2^(m-1) = (1/2)*2^m = (1/2)*2^(D/2)` messages.
So at least one link has congestion `(1/2)*2^(D/2)`.
