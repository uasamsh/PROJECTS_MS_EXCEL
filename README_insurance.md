# US Health Insurance Cost Analysis - Descriptive Statistics (Excel)

A full descriptive statistics project analyzing US health insurance charges across 1,000 records, reproducing the exact statistic set Excel's Data Analysis ToolPak produces — plus visualizations, all on one sheet.

![Project Preview](screenshot1.png)
![Project Preview](screenshot2.png)

## What this project does

- 1,000 records modeled on real-world US insurance cost patterns: **Age, Sex, BMI, Children, Smoker status, Region, Charges**
- A full **Descriptive Statistics table** (columns I onward, same sheet) for Age, BMI, Children, and Charges — the complete 16-statistic set matching Excel's Data Analysis ToolPak output:
  Mean, Standard Error, Median, Mode, Standard Deviation, Sample Variance, Kurtosis, Skewness, Range, Minimum, Maximum, Sum, Count, Largest(1), Smallest(1), Confidence Level(95.0%)
- **4 charts** on the same sheet:
  1. Average charges: smokers vs non-smokers (bar)
  2. Average charges by US region (bar)
  3. Age vs Charges (scatter) — shows cost rising with age
  4. BMI vs Charges (scatter) — shows cost impact of BMI, especially combined with smoking

## Why this dataset

Health insurance charges in the US are strongly driven by **age, BMI, and smoking status** — a well-known real-world pattern (smokers often pay 3-4x more than non-smokers for similar age/BMI). This dataset is synthetically generated to reflect those realistic relationships for practice purposes — it does not represent actual insurer records.

## A note on "N/A" in the Mode row

For the **Charges** column, Mode shows `N/A`. This is expected, not an error — Charges is a continuous decimal value, so exact duplicate values are rare across 1,000 rows, and Excel's `MODE()` has nothing to return when no value repeats. Age, BMI, and Children (which take on repeating whole/rounded values) show a real Mode.

## How it works (Excel skills used)

| Statistic | Formula |
| --- | --- |
| Mean | `=AVERAGE(range)` |
| Standard Error | `=STDEV(range)/SQRT(COUNT(range))` |
| Median | `=MEDIAN(range)` |
| Mode | `=MODE(range)` |
| Standard Deviation | `=STDEV(range)` |
| Sample Variance | `=VAR(range)` |
| Kurtosis | `=KURT(range)` |
| Skewness | `=SKEW(range)` |
| Range | `=MAX(range)-MIN(range)` |
| Minimum / Maximum | `=MIN(range)` / `=MAX(range)` |
| Sum / Count | `=SUM(range)` / `=COUNT(range)` |
| Largest(1) | `=LARGE(range,1)` |
| Smallest(1) | `=SMALL(range,1)` |
| Confidence Level(95.0%) | `=CONFIDENCE(0.05, STDEV(range), COUNT(range))` |

Helper summary tables (`AVERAGEIF`) feed the bar charts; the scatter charts plot raw Age/BMI against Charges directly from the data table.

## How to use

1. Download `US_Insurance_Descriptive_Statistics.xlsx`
2. Open in Microsoft Excel (best viewed in real Excel rather than lightweight online viewers, since some statistical functions render inconsistently elsewhere)
3. Review the Descriptive Statistics table for each metric
4. Explore the 4 charts to see how smoking, region, age, and BMI relate to insurance charges

## Skills demonstrated

- Full descriptive statistics suite (Data Analysis ToolPak-equivalent, built with formulas instead of the add-in so it stays live/dynamic)
- Conditional aggregation (`AVERAGEIF`)
- Multiple chart types (bar, scatter) on a single sheet
- Real-world-patterned synthetic data generation

## License

All rights reserved — see [`LICENSE`](LICENSE) for terms.
