# Revenue gauge, conditional formatting

The "Total Revenue and Previous Month Revenue" gauge on the Product
Dashboard changes color depending on whether current revenue is above or
below the previous month's value.

## 1. Add the measure

```dax
GaugeColor =
IF (
    [Total Revenue] >= [Previous Month Revenue],
    "#499442",   -- above target: soft green
    "#CE514D"    -- below target: soft red
)
```

Make sure this returns a valid hex string (including the `#`) in every case
, a stray `BLANK()` branch will make the conditional formatting silently
fall back to a default color instead of erroring.

## 2. Wire it up in Power BI

1. Select the gauge visual.
2. **Format visual** → **Color** (the fill/arc color) → click the **fx**
   (conditional formatting) icon.
3. **Format style**: `Field value`.
4. **What field should we base this on?**: `GaugeColor`.
5. **Summarization**: `First` (it's a single scalar value, not something to
   sum or average).
6. Apply.

## 3. Set the target marker color

Separately, set **Format visual** → **Target** → **Color** to `#52514E`
(neutral ink) rather than the default orange/red — now that red carries a
"below target" meaning on the arc itself, the reference line should read as
a neutral comparison marker, not a second status signal.
