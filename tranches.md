# Tranches

If you want to [treat colors equally](./design-principles.md#treat-colors-equally), entities have to be added to your game in roughly equal amounts across colors. Otherwise you risk neglecting colors, or playing favorites with colors. For example if your game has a 9-color system, then monocolor entities should to be added in batches of 9. Let's call one of those batches a _tranche_. Tranches are a basic building block of your game.

What other tranches might your game permit? If you allow colorless entities, they might be able to be added in single-entity tranches all by themselves. But if you want to ensure that colorless entities don't outnumber any given color, then they have to be added in 10-entity tranches - one colorless, and one of every color to balance it out. Tranches are how you enforce those sorts of constraints.

## Multicolor

Tranches have unique interactions with multicolor due to the design principle that [monocolor matters most](./design-principles.md#monocolor-matters-most). If multicolor entities featuring a given color should not outnumber monocolor entities of the same color, special consideration is required to ensure this rule is enforced.

If you use a color wheel and pairs or trios are only permitted for adjacent colors on the wheel, then each color exists in only two possible pairs or one possible trio. If you want to add an entity for each pair, you also have to add two monocolor entities per color, or one monocolor entity when adding trios. This is regardless if the number of colors in your system.

However if all pairs are required, the math is much more complex. The number of entities in a multicolor tranche scales sharply with the number of colors in the system.

### Dualcolor Tranches

Consider a 4-color system. It supports 6 [coequal](./multicolor/color-pairs.md#primacy-vs-coequality) pairs, and among those pairs each color is represented 3 times. If we wanted to add an entity for each pair, we'd have to add 3 monocolor entities per color to compensate. This leads to a tranche size of 18 entities.

This same logic applies to systems of any size. The following table illustrates how this math plays out for systems of 2 to 12 colors.

- **1E/C** - Monocolor Entities per Color
- **Σ1E** - Total monocolor entities per tranche
- **Σ2E** - Total monocolor entities per tranche

|  Colors  | Pairs | 1E/C | Σ1E | Σ2E | Tranche |
| :------: | ----: | ---: | --: | --: | ------: |
| **_2_**  |     1 |    1 |   2 |   1 |       3 |
| **_3_**  |     3 |    2 |   6 |   3 |       9 |
| **_4_**  |     6 |    3 |  12 |   6 |      18 |
| **_5_**  |    10 |    4 |  20 |  10 |      30 |
| **_6_**  |    15 |    5 |  30 |  15 |      45 |
| **_7_**  |    21 |    6 |  42 |  21 |      63 |
| **_8_**  |    28 |    7 |  56 |  28 |      84 |
| **_9_**  |    36 |    8 |  72 |  36 |     108 |
| **_10_** |    45 |    9 |  90 |  45 |     135 |
| **_11_** |    55 |   10 | 110 |  55 |     165 |
| **_12_** |    66 |   11 | 132 |  66 |     198 |

### Tricolor Tranches

Consider a 4-color system. It supports 4 [coequal](./multicolor/color-pairs.md#primacy-vs-coequality) trios, and among those trios each color is represented 3 times. If we wanted to add a entity for each trio, we'd have to add 3 monocolor entities per color to compensate. This leads to a tranche size of 16 entities. Note that this omits color pairs entirely.

This same logic applies to systems of any size. The following table illustrates how this math plays out for systems of 3 to 12 colors.

- **1E/C** - Monocolor entities per Color
- **Σ1E** - Total monocolor entities per tranche
- **Σ3E** - Total tricolor entities per tranche

| Colors | Trios | 1E/C | Σ1E | Σ3E | Tranche Size |
| :----: | :---: | :--: | :-: | :-: | :----------: |
|   3    |   1   |  1   |  3  |  1  |      4       |
|   4    |   4   |  3   | 12  |  4  |      16      |
|   5    |  10   |  6   | 30  | 10  |      40      |
|   6    |  20   |  10  | 60  | 20  |      80      |
|   7    |  35   |  15  | 105 | 35  |     140      |
|   8    |  56   |  21  | 168 | 56  |     224      |
|   9    |  84   |  28  | 252 | 84  |     336      |
|   10   |  120  |  36  | 360 | 120 |     480      |
|   11   |  165  |  45  | 495 | 165 |     660      |
|   12   |  220  |  55  | 660 | 220 |     880      |

### Dual-and-Tricolor Tranches

Consider the same 4-color system from the above examples. From among the 4 trios in the system, each pair is represented twice. If we want pairs to be represented at least as often by themselves as they are represented in trios, we need to add 2 dualcolor tranches for every 1 tricolor tranche we add. This ratio scales with the number of colors in the system.

This same logic applies to systems of any size. The following table illustrates how this math plays out for systems of 3 to 8 colors. After 8 colors, this becomes completely unmanageable.

- **2T** - Dualcolor tranches
- **3T** - Tricolor tranches

| Colors | 2T  | 3T  | Tranche Size |
| :----: | :-: | :-: | :----------: |
|   3    |  1  |  1  |      13      |
|   4    |  2  |  1  |      52      |
|   5    |  3  |  1  |     130      |
|   6    |  4  |  1  |     260      |
|   7    |  5  |  1  |     455      |
|   8    |  6  |  1  |     896      |
