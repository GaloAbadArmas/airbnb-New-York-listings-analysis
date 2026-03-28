# Data Quality Report

## Purpose

The goal of this report is to evaluate whether the dataset is reliable enough to support business interpretation.

Instead of assuming that all variables were valid, the analysis included a basic data quality validation process to identify issues that could affect the credibility of the findings.

---

## Main Issues Identified

| Issue | Description | Impact on Analysis | Action Taken |
|------|-------------|-------------------|--------------|
| Missing values | Important fields such as price and service fee contained nulls | Reduced completeness of core analytical variables | Rows with missing price were removed; other missing values were handled using variable-specific logic |
| Inconsistent labels | Borough labels such as `brookln` and `manhatan` were found | Fragmented categories and misleading group comparisons | Labels were standardized |
| Invalid negative values | Some records contained negative values in fields such as `minimum_nights` or `availability_365` | Logically impossible records | Invalid rows were removed |
| Unrealistic thresholds | Some values in `availability_365` were greater than 365 | Invalid yearly availability logic | Removed |
| Future dates | `last_review` contained future dates | Temporal inconsistency | Future dates were removed while preserving true missing values |
| Suspicious price behavior | Price distributions remained unusually similar across boroughs and room types | Limits the reliability of price-based conclusions | Price insights were flagged as cautionary |

---

## Reliability Assessment

The dataset is sufficiently usable for descriptive analysis of:

- listing distribution
- room type composition
- review activity
- annual availability

However, price-related variables appear less reliable for deeper market interpretation. The unusually similar price ranges across boroughs and room types suggest that the dataset may not fully reflect real-world pricing behavior.

For this reason, the final project separates findings into:

- **High-confidence insights**
- **Cautionary insights**

---

## Final Validation Statement

This analysis remains valid as a descriptive portfolio project because:

- major data quality issues were explicitly identified
- cleaning actions were documented
- unreliable variables were not overinterpreted
- conclusions were framed according to confidence level

This approach improves the credibility of the analysis and reflects good analytical judgment.
