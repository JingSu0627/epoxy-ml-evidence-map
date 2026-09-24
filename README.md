# Epoxy-ML Evidence Map

## Main Evidence Table

**[Download evidence.xlsx (Excel)](https://github.com/JingSu0627/epoxy-ml-evidence-map/raw/refs/heads/main/evidence.xlsx)**

**121 studies | 26 evidence fields | Study-level evidence and coding guide**

This is the primary dataset for the review. Start here for study details, model classifications, validation evidence, and data/code availability.

[View the workbook on GitHub](evidence.xlsx) | [Browse literature access links](docs/full_text_access.md)

## Overview

This repository provides a study-level evidence table supporting a review of machine learning for epoxy materials, including property prediction, state assessment, formulation and process optimization, and simulation acceleration.

The current [evidence.xlsx](evidence.xlsx) contains **121 study records and 26 columns** in the `Evidence table` worksheet, together with a `Coding guide` worksheet. The workbook is the source for the descriptive fields and coded counts below. This README was reconciled against it on 2026-09-24 without modifying the workbook. Reconciliation establishes agreement with the supplied extraction, not independent verification of every source publication or completeness of the literature search.

## Repository contents

```text
epoxy-ml-evidence-map/
|-- README.md
|-- evidence.xlsx
|-- docs/
|   `-- full_text_access.md
|-- data/
|   `-- full_text_access.json
`-- public_pdfs/
    `-- README.md
```

- `Evidence table`: one row per study, with 17 descriptive evidence fields followed by 9 controlled coding fields.
- `Coding guide`: coding rules and selected model-family and validation-hierarchy summaries.
- Both worksheets above are in the main `evidence.xlsx` file. The `docs/` and `data/` directories contain only the companion literature-access index, not alternative versions of the evidence table.
- [Full-text access index](docs/full_text_access.md): study identifiers, citations, source links, and access labels from the separate author-supplied access workbook, with a [machine-readable JSON version](data/full_text_access.json). This supplements access information only; it does not replace or recode `evidence.xlsx`.
- `public_pdfs/`: a redistribution notice only; no article PDFs are supplied. Public reading access does not establish redistribution permission. Unreviewed local full-text archives and PDFs are excluded from Git by explicit ignore rules.

## Literature search and selection status

This repository is a structured evidence map, not by itself evidence of a fully reproducible systematic review. The manuscript must explicitly identify its review type and support any claim of comprehensive coverage with the actual search and screening records.

The previous README reported the following search history. These details are retained as **author-reported information requiring confirmation against the original search records**, because the workbook contains included studies rather than a search or screening log.

| Item | Previously reported information | Verification status |
|---|---|---|
| Databases | Web of Science and Scopus | Search exports and database-specific queries are not supplied here |
| Publication window | 2010-2026 | Citation years in the workbook span this range; this does not verify the search limits |
| Final search date | 2026-06-30 | Exact execution date and search history require confirmation |
| Language and document types | English-language articles and reviews | The current corpus also contains conference-labelled records; actual eligibility rules and any exceptions require clarification |
| Database records retrieved | 465 | Not independently reconstructable from the included-study table |
| Duplicate records removed | 192 | Deduplication keys, procedure, and record-level decisions are not supplied |
| Unique records screened | 273 | Screening-stage log is not supplied |
| Records excluded | 155 | Title/abstract and full-text stages, exclusion reasons, and counts are not separated |
| Included from database set | 118 | Record-level origin is not encoded in the workbook |
| Additional studies | 3 | Identities, discovery route, dates, and screening decisions require confirmation |
| Final corpus | 121 | Verified as 121 populated study rows in `Evidence table` |

The reported arithmetic is consistent: `465 - 192 = 273`, `273 - 155 = 118`, and `118 + 3 = 121`. Arithmetic consistency does not establish that the search or screening history is reproducible.

Before describing the search as reproducible, provide the complete executed query for each database, searched fields, platform/collection, exact search date, date/language/document-type filters, deduplication procedure, inclusion and exclusion criteria, stage-specific screening counts and reasons, and the procedure actually used to resolve uncertain cases. Also reconcile the three additional records with the original search cutoff. Do not reconstruct historical search strings or screening decisions from the final corpus alone.

## Scope and record identification

The four application groups above describe the review's scope; **there is no separate task-group column** in the workbook. Relevant records can instead be located through `Epoxy system`, `Prediction target`, `Material representation`, and `Model type`.

There is no separate `Study ID`, publication-type, DOI/link, full-text-status, or notes column. Citation details and DOI strings are embedded in `Citation`. The current table contains 119 distinct DOI strings after case normalization and removal of DOI URL prefixes, and two records marked `DOI: NR`: Sunder et al. (2025), on processability and flame retardancy, and Theim et al. (2021), on nano-reinforced epoxy surfaces. No identical citation strings or repeated normalized DOI strings were found. This check does not exclude different publications reporting overlapping datasets or duplicate publications under different metadata.

Use the DOI, or the complete citation when no DOI is available, to identify a study. Spreadsheet row numbers are version-specific locators, not stable study identifiers. The separate [access index](docs/full_text_access.md) supplies EML identifiers and source links, including a Zenodo link for Sunder et al. and a proceedings DOI for Theim et al.; these additions have not been written back into the unchanged evidence workbook. Neither workbook establishes redistribution permission for every local PDF.

## Spreadsheet fields

The names below match the 26 headers in `Evidence table`, in column order.

| Column | Field | Description |
|---|---|---|
| A | `Citation` | Bibliographic description, usually including a DOI; not uniformly a complete formatted reference |
| B | `Epoxy system` | Material, composite, coating, adhesive, or simulation system studied |
| C | `Source of the data` | Experimental, simulation, literature-derived, or combined data provenance |
| D | `Number of individual records` | Reported dataset size or explanatory text; may contain several task-specific counts |
| E | `Number of unique formulations` | Independent formulation count where identifiable, otherwise explanatory or missing-information text |
| F | `Number of specimens or batches (where available)` | Specimen/batch information, not-applicable statements, or missing-information text |
| G | `Input variables` | Composition, processing, molecular, environmental, or other predictors |
| H | `Prediction target` | Property, material state, design objective, or simulation response |
| I | `Material representation` | Molecular, formulation, network, process, measurement, or other descriptors |
| J | `Model type` | Descriptive model names, combinations, and reported model comparisons |
| K | `Data-splitting strategy` | Reported partition, cross-validation, and testing details |
| L | `Optimization procedure` | Feature selection, hyperparameter tuning, and material/process optimization details |
| M | `Reported metrics` | Extracted metrics and values, with qualifications where available |
| N | `Treatment of uncertainty` | Descriptive uncertainty and applicability-domain information |
| O | `External or prospective validation` | Narrative account of validation targets and procedures |
| P | `Experimental verification` | Narrative account of experimental checks; not a uniform binary flag |
| Q | `Availability of data and code` | Narrative availability statements; does not consistently provide repository URLs |
| R | `Controlled model family` | Semicolon-separated family labels for study-level counting |
| S | `Split unit` | Controlled split-unit labels; multiple documented designs may be listed |
| T | `Highest evidence tier` | Single highest assigned evidence level, or `NA: No standalone predictor` |
| U | `External validation` | Controlled external-validation flag |
| V | `Prospective validation` | Controlled prospective-validation flag |
| W | `Closed loop` | Controlled repeated-feedback flag |
| X | `Formal UQ` | Controlled formal uncertainty-quantification flag |
| Y | `Public data` | Controlled public-data flag |
| Z | `Public code` | Controlled public-code flag |

The first 17 fields cover the information categories requested for a study-level evidence table. Presence of a field does not imply complete extraction: for example, 83 of 121 entries in column F are exactly `Not reported in the current extraction`. Dataset-size fields are mixed text rather than consistently numeric variables; do not sum them without study-specific interpretation, and do not equate measurement records with independent formulations, specimens, or batches.

`NR` and phrases such as `Not reported in the current extraction` identify missing or unresolved extracted information, not proof that the original article omitted it. `NA` means not applicable. For conservative interpretation, describe `No` in a controlled field as "not coded Yes in this extraction" unless the descriptive evidence supports a definite negative. Keep `Unclear` and `NA` separate from `No`.

## Coding and counting rules

The `Coding guide` describes conservative recoding from the descriptive fields. Model capability, dataset size, or a high reported score alone is not evidence of a particular validation procedure or formal uncertainty analysis.

### Model families

`Controlled model family` is multi-label. Split entries at semicolons, trim whitespace, and count each study at most once per family. Count documented component families for hybrid or multi-model studies rather than counting each algorithm, fitted model, or performance result. Optimization and interpretation procedures are not themselves predictor families.

The stored vocabulary is `Neural networks`, `Tree-based models`, `Kernel methods`, `Linear/regularized regression`, `Unsupervised methods`, `Other`, and `No standalone predictor`. A detailed algorithm-to-family crosswalk is not supplied; the current counts reproduce the stored assignments rather than independently recoding model names.

The model-family denominator is **120 studies**, excluding Shafe et al. (2022), DOI `10.1016/j.polymer.2022.124577`, which is coded `No standalone predictor`. It remains part of the full 121-study evidence map. The 120-study subset also contains unsupervised and other methods; it should not be described as 120 supervised prediction studies.

### Validation and reliability

`Split unit` uses `Record`, `Specimen/batch`, `Formulation`, `Source`, `Sequential/no fixed split`, `Unclear/unreported`, and `Not applicable`. Multiple explicit designs may coexist, but an unclear label should not coexist with an explicit split unit. Currently 81 studies are labelled `Unclear/unreported`; absence of a documented grouping must not be presented as confirmed random splitting.

The highest-tier ordering is `6 > 5 > 4B > 4A > 3B > 3A > 2 > 1`, with one tier per assigned study. It records the strongest coded evidence, not every validation design used by that study. For example, four studies have a `Formulation` split label, but only one has Tier 3A as its highest tier.

The guide defines independent external validation as evidence not used for model development; prospective validation as testing a subsequently prepared, measured, or simulated candidate; and a closed loop as repeated model-selection-experiment feedback. It defines formal UQ as an explicit predictive distribution, interval, posterior uncertainty, conformal prediction, or bootstrap uncertainty analysis. Public data/code require access without contacting the authors. These definitions describe the intended rules; the reconciliation limitations below still apply to their implementation.

## Recomputed workbook summaries

These are frequencies of the **current stored labels**, not independently adjudicated estimates for the entire field. Percentages are rounded to one decimal place.

### Model-family frequency

| Controlled model family | Studies | Percentage of 120 |
|---|---:|---:|
| Neural networks | 72 | 60.0% |
| Tree-based models | 43 | 35.8% |
| Kernel methods | 30 | 25.0% |
| Linear/regularized regression | 26 | 21.7% |
| Unsupervised methods | 7 | 5.8% |
| Other | 3 | 2.5% |

The total is 181 study-family memberships, not 181 unique papers; percentages need not sum to 100%. The `Coding guide` lists the first five families but omits the three `Other` assignments from its summary. They are included here so the README accounts for every assigned family. `No standalone predictor` contributes one further study to the full corpus, outside this denominator.

### Highest assigned evidence tier

| Stored tier | Studies | Percentage of 120 assigned studies |
|---|---:|---:|
| Tier 6: Closed-loop experimental design | 5 | 4.2% |
| Tier 5: Prospective experimental validation | 20 | 16.7% |
| Tier 4B: Independent external validation | 8 | 6.7% |
| Tier 4A: Chemistry-aware validation | 0 | 0.0% |
| Tier 3B: Source-grouped validation | 1 | 0.8% |
| Tier 3A: Formulation-grouped validation | 1 | 0.8% |
| Tier 2: Specimen/batch-grouped validation | 1 | 0.8% |
| Tier 1: Internal validation (record-level or unclear) | 84 | 70.0% |

One additional study is `NA: No standalone predictor`. A zero Tier 4A count means no study has that **highest assigned tier**; it does not independently establish the absence of chemistry-aware evaluation in all papers. The split-unit vocabulary has no separate chemistry-aware label, so a corpus-wide incidence claim needs source-level checking.

### Controlled flags across the complete corpus

| Field | Yes | No | Unclear | NA | Yes / 121 |
|---|---:|---:|---:|---:|---:|
| External validation | 8 | 113 | 0 | 0 | 6.6% |
| Prospective validation | 25 | 96 | 0 | 0 | 20.7% |
| Closed loop | 5 | 116 | 0 | 0 | 4.1% |
| Formal UQ | 6 | 110 | 5 | 0 | 5.0% |
| Public data | 45 | 62 | 6 | 8 | 37.2% |
| Public code | 8 | 113 | 0 | 0 | 6.6% |

The full-corpus denominator includes all 121 studies and retains unknown and not-applicable entries. Do not mix these percentages with the 120-study model-family or highest-tier percentages. Prospective validation includes all five closed-loop studies: the 25 prospective flags are not 25 additional papers beyond the five closed-loop papers. Formal UQ is not the same as demonstrated calibration or interval coverage.

## Interpretation limits and outstanding checks

The workbook was preserved unchanged. The following issues cannot be resolved by relabelling the README alone:

1. **External-validation definitions and assignments need reconciliation.** All eight controlled external-validation positives are Tier 4B, and all 25 prospective positives are coded external `No`. However, descriptive entries such as Jafari et al. (2026), row 2, explicitly state external and prospective validation, while column U says `No`. Thus 8/121 is the frequency of the stored external flag, not an established incidence of every form of independent validation. Confirm whether exclusivity was intentional and document a consistent rule before making a scientific claim.
2. **Simulation validation is not necessarily experimental verification.** For example, Giuntoli et al. (2021), row 115, and Shafe et al. (2024), row 116, are coded external `Yes`, while the descriptive fields identify simulation-based validation and no new experiments. In addition, the prospective coding rule allows simulated candidates, whereas the Tier 5 label says experimental validation. These distinctions require article-level adjudication rather than treating all external/prospective flags as laboratory evidence.
3. **Experimental verification and prospective validation are not interchangeable.** Some column P entries say `No new prospective experiment beyond the paper's own experimental validation`. This is not a simple `No` to experimental verification. A count of experimentally verified studies cannot be obtained by treating the opening word of every entry as a binary code.
4. **Traceability is incomplete.** There are no dedicated page/table/figure evidence locators, stable study IDs, or uniform data/code repository links. Citation and DOI duplicate checks do not replace a manuscript-wide reference and claim audit. Coding uncertainties and model-family assignments still require explicit adjudication records.
5. **Figure references need manuscript reconciliation.** The workbook guide calls its model-family summary `Figure 5`; the supplied reviewer comments refer to model-family frequencies as Figure 4 and a separate attribution plot as Figure 5. Confirm the final numbering and regenerate the actual figures from the agreed dataset and counting rules. No manuscript figure was regenerated during this README audit.

The corpus includes the specifically highlighted Pruksawan (2019), Qiu (2022), Liu (2022), and Sindu and Hamaekers (2025) studies. Their presence addresses those examples of missing records, but does not demonstrate that the search was rerun systematically or that the manuscript discussion and citations have been corrected.

## Reproducing the stored counts

The following read-only Python example requires `openpyxl` and is run from the repository directory. It reproduces the counts from `Evidence table`; it does not save, recode, or overwrite the workbook.

```python
from collections import Counter
from openpyxl import load_workbook

workbook = load_workbook("evidence.xlsx", read_only=True, data_only=True)
try:
    rows = workbook["Evidence table"].iter_rows(values_only=True)
    headers = next(rows)
    studies = [dict(zip(headers, row)) for row in rows if row[0]]
finally:
    workbook.close()

def labels(value):
    return {label.strip() for label in (value or "").split(";") if label.strip()}

model_studies = [
    study for study in studies
    if "No standalone predictor" not in labels(study["Controlled model family"])
]
families = Counter(
    family for study in model_studies
    for family in labels(study["Controlled model family"])
)
print("Full corpus:", len(studies))
print("Model-family denominator:", len(model_studies))
for family, count in sorted(families.items()):
    print(family, count, f"{100 * count / len(model_studies):.1f}%")
for field in (
    "Highest evidence tier", "External validation", "Prospective validation",
    "Closed loop", "Formal UQ", "Public data", "Public code",
):
    print(field, dict(Counter(study[field] for study in studies)))
print("Split-unit memberships:", dict(Counter(
    unit for study in studies for unit in labels(study["Split unit"])
)))
```

## Publication status

This is a working evidence-map package, hosted at [JingSu0627/epoxy-ml-evidence-map](https://github.com/JingSu0627/epoxy-ml-evidence-map). It supplies a machine-readable extraction and documented counting rules, but the search records, coding reconciliation, source-level evidence checks, and manuscript integration remain necessary before claiming that the review's reproducibility concerns have been fully addressed. No archived release or persistent identifier has been issued yet.

Before submission, add the confirmed search/selection documentation, resolve the flagged coding issues without silently changing historical evidence, reconcile all quantitative statements and figure captions with their denominators, and cite a versioned repository release in the manuscript and supporting-information description. Do not claim that this README alone resolves manuscript-level requests about chemical representations, evaluation methods, explainability, or reference accuracy.
