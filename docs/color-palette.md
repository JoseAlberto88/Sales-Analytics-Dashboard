# Color palette reference

All palettes below were generated in OKLCH color space and validated with a
colorblind-safety script (protanopia/deuteranopia simulation, OKLab ΔE) before
being applied. "Adjacent" means the check covers colors that sit next to each
other in the chart (bars, wedges); "all-pairs" means every color was checked
against every other color, a stricter bar.

## Customer Dashboard. Total Orders donut (by Occupation)

Six-slot categorical palette, validated on adjacent pairs (worst ΔE 8.1
deutan / 16.5 normal-vision).

| Category | Hex |
|---|---|
| Professional | `#70A7EF` |
| Skilled Manual | `#FF7641` |
| Management | `#00C681` |
| Clerical | `#DA9E3F` |
| Manual | `#E580A5` |
| (Blank) | `#61B55C` |

## Product Dashboard. Total Orders by Category (bar chart)

Three-slot categorical palette, deliberately distinct from the donut's
palette so Category and Occupation read as separate dimensions. Passes even
the stricter all-pairs check (worst ΔE 8.7 deutan / 17.3 normal-vision).

| Category | Hex |
|---|---|
| Accessories | `#9B99F3` (soft violet) |
| Bikes | `#F07F77` (soft coral) |
| Clothing | `#16BBBC` (soft teal) |

## Product Dashboard — Total Revenue area chart

Single continuous series → one hue, light-to-dark, not multiple colors
(the series has no legend; there's nothing for separate colors to identify).

| Role | Hex |
|---|---|
| Area fill (wash under the line) | `#B7D3F6` |
| Line stroke | `#2A78D6` |

## Product Dashboard — Revenue gauge (current vs. previous month)

Conditional status color: green when current revenue is at/above the prior
month, red when below. See
[`gauge-conditional-formatting.md`](gauge-conditional-formatting.md) for the
DAX measure and Power BI setup. Deliberately softer than a saturated
red/green pair to match the dashboard's pastel tone, while still clearing
3:1 contrast against the card background.

| Role | Hex | Contrast vs. card |
|---|---|---|
| Above target (good) | `#499442` | 3.3:1 |
| Below target (critical) | `#CE514D` | 3.8:1 |
| Target marker line (neutral) | `#52514E` | 7.1:1 |

**Accessibility note:** green vs. red is the single hardest pair for
red-green colorblindness — no hue choice fixes that, since it's the
definition of the condition. Because only one color shows at a time here
(not side-by-side, unlike a legend), the risk is lower, but pairing the
color with a small directional icon or label (e.g. "▲ Above last month" /
"▼ Below last month") is the standard mitigation if this gauge needs to be
scannable by everyone at a glance.

## Method

Colors were built in OKLCH (perceptually uniform lightness/chroma/hue), then
checked against:

1. Lightness band (readable, not too light/dark for the surface)
2. Chroma floor (saturated enough to read as a color, not gray)
3. CVD separation — simulated protanopia/deuteranopia ΔE in OKLab, target ≥ 8
4. Normal-vision floor — unsimulated ΔE ≥ 15, so full-color readers can tell
   neighbors apart too
5. Contrast vs. the chart surface (≥ 3:1, or paired with visible labels if
   below that)
