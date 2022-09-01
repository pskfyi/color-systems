# Multicolor - Monocolor Ratios

Given the [design principles](../design-principles.md) established, particularly [Treat Colors Equally](../design-principles.md#treat-colors-equally) and [Monocolor Matters Most](../design-principles.md#monocolor-matters-most),

## Color Pairs

An interesting corollary emerges from these:

> There is a minimum 2:1 ratio of total monocolor:dualcolor cards, regardless of
> the number of colors in the system.

## Simplest Systems

The simplest system involves 1 monocolor card per color and 1 dual-color card
per pair.

## Tranches

We can think of these simplest systems as forming tranches. If I wanted to add
an additional dualcolor card to the set, I'd need to add a proportional number
of monocolor cards as well. I can't add just the dualcolor card. There's a
minimum tranche size of 3 cards, when a dualcolor card is desired.

## Breakdown

- **C** - Colors
- **P** - Color Pair; Also total dualcolor cards per tranche
- **M/C** - Monocolor Cards per Color
- **Σ M** - Total monocolor cards per tranche
- **Σ** - Total cards per tranche

|  C  |  P  | M/C | Σ M |  Σ  |
| :-: | :-: | :-: | :-: | :-: |
|  2  |  1  |  1  |  2  |  3  |
|  3  |  3  |  2  |  6  |  9  |
|  4  |  6  |  3  | 12  | 18  |
|  5  | 10  |  4  | 20  | 30  |
|  6  | 15  |  5  | 30  | 45  |
|  7  | 21  |  6  | 42  | 63  |
| ... | ... | ... | ... | ... |
| 12  | 66  | 11  | 132 | 198 |

## Elaboration

Let's examine the 5-color system as an example. Let's use Magic's 5 colors:
White, Blue, Black, Red, and Green.

In this system, there are 10 color pairs, for example Red/Blue and Blue/White.
Accordingly, a minimum tranche would have 10 dualcolor cards total.

Each color is represented 4 times amongst the color pairs. For example for Red,
we have Red/Green, Red/Blue, Red/Black, and Red/White.

If Red needs to have at least as many monocolor cards, then it needs at least 4
cards. If we apply the same principles to the 5 colors, we need 4 monocolor
cards each, for 20 cards total.

So our minimum tranche has 10 dualcolor cards and 20 monocolor cards total: a
2-to-1 ratio.
