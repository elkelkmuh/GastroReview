# Artificial Intelligence in Gastroenterology: Evidence Repository

This repository contains the bibliographic search exports and structured evidence tables supporting the narrative review:

> **Artificial Intelligence in Gastroenterology: Towards Explainable, Generalisable and Clinically Actionable Decision Support**

The review examines why strong retrospective model performance does not necessarily translate into reliable clinical decision support. The evidence is organised around three translational requirements:

1. **Explainability** — whether an AI output is technically interpretable and clinically understandable.
2. **Generalisability** — whether performance is maintained across institutions, populations, devices and time.
3. **Clinical actionability** — whether AI changes clinical decisions, workflows, resource use or patient outcomes.

Communication, meaningful human oversight and lifecycle governance are considered cross-cutting requirements.

## Repository Contents

### Thematic Bibliographic Datasets

The `.xls` files are Web of Science bibliographic exports. Each file contains a `savedrecs` worksheet with bibliographic fields such as authors, article title, abstract, keywords, affiliations, publication year, DOI, PubMed ID and Web of Science accession number.

| File                                                                  | Evidence theme                                       | Records |
| --------------------------------------------------------------------- | ---------------------------------------------------- | ------: |
| `4A. Human-centred and clinically relevant explainability.xls(3).xls` | Human-centred and clinically relevant explainability |     141 |
| `4B. Validated technical explainability.xls(3).xls`                   | Validated technical explainability                   |     315 |
| `5A. Explicit external and multicentre validation.xls(3).xls`         | External and multicentre validation                  |     130 |
| `5B. Dataset shift and transportability.xls(3).xls`                   | Dataset shift and transportability                   |      91 |
| `6A. Clinical impact and prospective implementation.xls(3).xls`       | Clinical impact and prospective implementation       |     156 |
| `6B1. Real clinical application and workflow..xls`                    | Real-world clinical application and workflow         |     198 |
| `6B2. Health-economic evidence.xls(3).xls`                            | Health-economic evidence                             |     105 |
| `7A. Consensus guidelines and position statements.xls(3).xls`         | Consensus guidelines and position statements         |     120 |
| `7B. Governance regulation and human oversight.xls(3).xls`            | Governance, regulation and human oversight           |     206 |
| `A Pankreas kanseri ve pankreatik lezyonlar(1).xls`                   | Pancreatic cancer and pancreatic lesions             |     214 |
| `A1. Fibrosis assessment.xls`                                         | Liver fibrosis assessment                            |      53 |
| `B — Pancreatitis and biliary decision support.xls`                   | Pancreatitis and biliary decision support            |     195 |
| `B1. HCC detection and surveillance.xls`                              | Hepatocellular carcinoma detection and surveillance  |     115 |
| `B2. HCC recurrence, prognosis, and treatment response..xls`          | HCC recurrence, prognosis and treatment response     |      73 |

Record totals exclude the header row. The thematic searches overlap; therefore, these values should not be summed to calculate the number of unique studies.

### Curated Pancreaticobiliary Evidence Matrix

`Pancreaticobiliary_Clinical_Evidence.xlsx` contains the record-level screening and evidence-characterisation results for the pancreaticobiliary component of the review.

| Worksheet                   | Purpose                                                      | Records |
| --------------------------- | ------------------------------------------------------------ | ------: |
| `All_397_Screening`         | Complete deduplicated screening set                          |     397 |
| `Included_Clinical_Studies` | Included primary human clinical studies                      |      87 |
| `Pancreatic_EUS_and_Cysts`  | Pancreatic EUS and cystic-lesion studies                     |      17 |
| `Biliary_Endoscopy`         | ERCP, cholangioscopy and biliary-stricture studies           |      11 |
| `Acute_Pancreatitis`        | Acute-pancreatitis prediction and decision-support studies   |      59 |
| `Anchor_Studies`            | Methodologically or clinically important studies             |       8 |
| `Excluded_Records`          | Excluded records with exclusion reasons                      |     307 |
| `Unclear_Author_Review`     | Borderline records requiring author assessment               |       3 |
| `Quality_Control`           | Deduplication, eligibility and quality-control documentation |       — |
| `Summary`                   | Screening totals and consistency checks                      |       — |

The evidence-characterisation fields include clinical area, study design, retrospective or prospective status, centres and countries, sample size, data modality, AI method, supported clinical decision, validation strategy, performance, comparator, explainability, applicability, limitations, decision rationale and a concise narrative summary.

## Review Design

This work is a focused, structured narrative review informed by the SANRA framework.

Web of Science Core Collection, Scopus and PubMed were searched through **11 July 2026**. The principal clinical searches covered publications from 2018 to 2026. Searches for recent field-level reviews covered 2021–2026, while the digestive-disease burden search covered 2020–2026.

Records were deduplicated hierarchically using:

1. DOI;
2. database-specific identifiers, including Web of Science accession numbers, Scopus EIDs and PubMed IDs; and
3. normalised full-title matching when persistent identifiers were unavailable.

Eligible evidence addressed substantive AI-enabled clinical or communication tasks in gastroenterology, including detection, diagnosis, prognostication, treatment selection, disease monitoring, procedural support, workflow optimisation, patient education and clinician–patient communication.

The pancreaticobiliary subset comprised 409 retrieved records, 12 cross-file duplicates and 397 unique records. Following title and abstract assessment, 87 studies were included, 307 were excluded and 3 required further author review.

These counts describe the curated pancreaticobiliary evidence matrix and should not be interpreted as a PRISMA systematic-review flow for the complete narrative review.

## How to Use the Files

The files can be examined using Microsoft Excel, LibreOffice Calc, Python or R. When importing legacy `.xls` files, bibliographic identifiers should preferably be retained as text to prevent alteration of leading zeros or long identifier values.

### Python Example

```python
import pandas as pd

evidence = pd.read_excel(
    "Pancreaticobiliary_Clinical_Evidence.xlsx",
    sheet_name="Included_Clinical_Studies"
)

selected_columns = [
    "Baslik",
    "Yil",
    "DOI",
    "Dogrulama",
    "Uygulanabilirlik"
]

print(evidence[selected_columns].head())
```

### R Example

```r
library(readxl)

evidence <- read_excel(
  "Pancreaticobiliary_Clinical_Evidence.xlsx",
  sheet = "Included_Clinical_Studies"
)
```

## Interpretation Notes

* The thematic bibliographic files are search outputs rather than independent study cohorts.
* A study may appear in multiple datasets because explainability, external validation, implementation and governance are overlapping concepts.
* `NR` indicates information that was not reported or could not be determined at the assessment level.
* Inclusion in the evidence matrix does not indicate low risk of bias or readiness for clinical deployment.
* Performance values should be interpreted alongside study design, validation setting, comparator and clinical endpoint.
* Evidence was synthesised narratively because of heterogeneity in clinical tasks, populations, AI architectures, comparators and outcomes.
* Citation counts were used only for literature navigation and were not treated as indicators of methodological quality.
* The repository does not contain individual-level or identifiable patient data.

## Authors

* İsmail Baydili
* Burak Tasci — corresponding author
* Sengul Dogan
* Turker Tuncer

**Correspondence:** [btasci@firat.edu.tr](mailto:btasci@firat.edu.tr)

## Citation

If you use this repository, please cite the associated article:

```text
Baydili I, Tasci B, Dogan S, Tuncer T. Artificial Intelligence in
Gastroenterology: Towards Explainable, Generalisable and Clinically Actionable
Decision Support. Journal information and DOI will be added after publication.
```

## Data Provenance and Responsible Reuse

The bibliographic exports contain metadata retrieved from Web of Science and may include identifiers associated with Scopus and PubMed records. Users are responsible for complying with the terms of the source databases and should cite the original publications when reusing study-level information.

No reuse licence has currently been assigned to this repository. Redistribution and reuse remain subject to applicable copyright and database terms. A repository licence should be selected only after confirming that redistribution of the source-database exports is permitted.

## Funding

This research received no external funding.

## Ethics Statement

Institutional review board approval and informed consent were not applicable because this study reviewed previously published literature and did not use identifiable individual-level patient data.

## Conflicts of Interest

The authors declare no conflicts of interest.
