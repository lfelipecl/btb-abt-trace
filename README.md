## Bovine Tuberculosis Surveillance: Risk-Based Trace-back Prioritization

This repository contains the code and data structure for the paper: "Improving Bovine Tuberculosis Surveillance Through Risk-Based Prioritization of Slaughterhouse Triggered Trace-back Investigations".

All necessary packages and dependencies are located in the requirements.txt file. Install them using:

`pip install -r requirements.txt`

## Data Structure
The raw datasets are located in the original_data/ directory.


## Codebook of original data files and variables:

| Name | Type | Source | Description |
| :--- | :--- | :--- | :--- |
| **adf** | file | adf.parquet | This file contains data on slaughtered cattle that presented suspicious tuberculosis lesions, including the contact route through the farms where they stayed during their lifetime. |
| vig_id | variable | adf/vig_id | Unique identifier for the lesion collection procedure. |
| vig_date | variable | adf/vig_date | Collection date of the lesion sample. |
| result | variable | adf/result | qPCR (quantitative Polymerase Chain Reaction) confirmation result for bovine tuberculosis (Mycobacterium bovis). |
| result_date | variable | adf/result_date | Release date of the laboratory diagnostic result |
| bovine_id | variable | adf/bovine_id | Unique identifier of the bovine sampled (also know as sentinel) |
| farm_id | variable | adf/farm_id | Unique identifier of the contact farm |
| contact_order | variable | adf/contact_order | Sequential order of contact between the sentinel animal and the contact farm, tracked retrospectively from the slaughterhouse back to the animal's birth. |
| last_contact | variable | adf/last_contact | Date of the last contact between the animal and the contact farm. |
| exposure_duration | variable | adf/exposure_duration | Total period of exposure during which the animal remained on the contact farm. |
| herd_size | variable | adf/herd_size | Time-weighted average of the herd size on the contact farm during the exposure period. |
| **fex** | file | fex.parquet | This file contains field examination records for all animals within the contact farms. |
| farm_id | variable | fex/farm_id | Unique identifier for the farm, consistent with other datasets. |
| field_exame_id | variable | fex/field_exame_id | Unique identifier for the field examination. |
| field_exame_date | variable | fex/field_exame_date | Date when the field examination was performed. |
| pos | variable | fex/pos | Number of animals that tested positive in the field examination. |
| nex | variable | fex/nex | Number of animals examined (tested) during the procedure. |
| Ntotal | variable | fex/Ntotal | Total herd size on the farm at the date of the examination. |

## Analysis workflow

To replicate the study findings, execute the scripts in the following sequence:

1. modeling.ipynb
2. classifying_risk.ipynb
3. apparent_prevalence_apv.ipynb
4. model_x_field.ipynb

All datasets provided in this repository have been de-identified to ensure anonymity, in compliance with Brazilian data protection laws (Lei Geral de Proteção de Dados - LGPD).
