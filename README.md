## Bovine Tuberculosis Surveillance: Risk-Based Trace-back Prioritization

This repository contains the code and data structure for the paper: "Improving Bovine Tuberculosis Surveillance Through Risk-Based Prioritization of Slaughterhouse Triggered Trace-back Investigations".

Prerequisites
All necessary packages and dependencies are located in the requirements.txt file. Install them using:


pip install -r requirements.txt

## Data Structure
The raw datasets are located in the original_data/ directory.




## Codebook of original data files and variables:

"| Name | Type | Source | Description |\n",
    "| :--- | :--- | :--- | :--- |\n",
    "| **adf** | file | adf.parquet | <br>This file contains data on slaughtered cattle that presented suspicious tuberculosis lesions, including the contact route through the farms where they stayed during their lifetime. <br><br> |\n",
    "| vig_id | variable | adf/vig_id | <br>Unique identifier for the lesion collection procedure. <br><br> |\n",
    "| vig_date | variable | adf/vig_date | <br>Collection date of the lesion sample.<br><br> |\n",
    "| result | variable | adf/result | <br>qPCR (quantitative Polymerase Chain Reaction) confirmation result for bovine tuberculosis (Mycobacterium bovis).<br><br> |\n",
    "| result_date | variable | adf/result_date | <br>Release date of the laboratory diagnostic result<br><br> |\n",
    "| bovine_id | variable | adf/bovine_id | <br>Unique identifier of the bovine sampled (also know as sentinel) <br><br> |\n",
    "| farm_id | variable | adf/farm_id | <br> Unique identifier of the contact farm <br><br> |\n",
    "| contact_order | variable | adf/contact_order | <br>Sequential order of contact between the sentinel animal and the contact farm, tracked retrospectively from the slaughterhouse back to the animal's birth.<br><br> |\n",
    "| last_contact | variable | adf/last_contact | <br>Date of the last contact between the animal and the contact farm.<br><br> |\n",
    "| exposure_duration | variable | adf/exposure_duration | <br>Total period of exposure during which the animal remained on the contact farm.<br><br> |\n",
    "| herd_size | variable | adf/herd_size | <br>Time-weighted average of the herd size on the contact farm during the exposure period.<br><br> |\n",
    "| **fex** | file | fex.parquet | <br> This file contains field examination records for all animals within the contact farms. <br><br> |\n",
    "| farm_id | variable | fex/farm_id | <br> Unique identifier for the farm, consistent with other datasets. <br><br> |\n",
    "| field_exame_id | variable | fex/field_exame_id | <br> Unique identifier for the field examination. <br><br> |\n",
    "| field_exame_date | variable | fex/field_exame_date | <br> Date when the field examination was performed. <br><br> |\n",
    "| pos | variable | fex/pos | <br> Number of animals that tested positive in the field examination. <br><br> |\n",
    "| nex | variable | fex/nex | <br> Number of animals examined (tested) during the procedure. <br><br> |\n",
    "| Ntotal | variable | fex/Ntotal | <br> Total herd size on the farm at the date of the examination. <br><br> |"

## Analysis workflow

To replicate the study findings, execute the scripts in the following sequence:

1. Modeling.ipynb
2. classifying_risk.ipynb
3. apparent_prevalence_apv.ipynb
4. model_x_field.ipynb
5. model_graphics.ipynb

All datasets provided in this repository have been de-identified to ensure anonymity, in compliance with Brazilian data protection laws (Lei Geral de Proteção de Dados - LGPD).
