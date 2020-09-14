# drought

## Principles
<small>(ref https://medium.com/swlh/how-to-structure-a-python-based-data-science-project-a-short-tutorial-for-beginners-7e00bff14f56)</small>

1. A clear data pipeline (starting with unchanged raw data): This means that the data is transformed in stages. For example, the raw data is fed into a notebook that transforms and saves an intermediate (cleaned) dataset. The intermediate dataset is then read into a processing notebook where feature engineering takes place. The new dataset (with features) is then saved before moving onto the next stage.
2. Separation of concerns (seperate files that do different things): In computer science, separation of concerns (SoC) is a design principle for separating a computer program into distinct sections, so that each section addresses a separate concern.
3. Standard file naming conventions: In order to avoid the terrible df/ df_new/df_new_final scenario listed above, it’s important to build one consistent file naming system before you start coding.

This project follows the project structure of "Data Science for Social Good"...

├── README.md          <- The top-level README for developers.
├── conf               <- Space for credentials
│
├── data
│   ├── 01_raw         <- Immutable input data
│   ├── 02_intermediate<- Cleaned version of raw
│   ├── 03_processed   <- Data used to develop models
│   ├── 04_models      <- trained models
│   ├── 05_model_output<- model output
│   └── 06_reporting   <- Reports and input to frontend
│
├── docs               <- Space for Sphinx documentation
│
├── notebooks          <- Jupyter notebooks. Naming convention is
|                         date YYYYMMDD (for ordering),
│                         the creator's initials, and a short `-` 
|                         delimited description.
│
├── references         <- Data dictionaries, manuals, etc. 
│
├── results            <- Final analysis docs.
│
├── requirements.txt   <- The requirements file for reproducing the 
|                         analysis environment.
│
├── .gitignore         <- Avoids uploading data, credentials, 
|                         outputs, system files etc
│
└── src                <- Source code for use in this project.
    ├── __init__.py    <- Makes src a Python module
    │
    ├── d00_utils      <- Functions used across the project
    │   └── remove_accents.py
    │
    ├── d01_data       <- Scripts to reading and writing data etc
    │   └── load_data.py
    │
    ├── d02_intermediate<- Scripts to transform data from raw to 
    |   |                  intermediate
    │   └── create_int_payment_data.py
    │
    ├── d03_processing <- Scripts to turn intermediate data into 
    |   |                 modelling input
    │   └── create_master_table.py
    │
    ├── d04_modelling  <- Scripts to train models and then use 
    |   |                  trained models to make predictions. 
    │   └── train_model.py
    │
    ├── d05_model_evaluation<- Scripts that analyse model 
    |   |                      performance and model selection.
    │   └── calculate_performance_metrics.py
    │    
    ├── d06_reporting  <- Scripts to produce reporting tables
    │   └── create_rpt_payment_summary.py
    │
    └── d07_visualisation<- Scripts to create frequently used plots
        └── visualise_patient_journey.py



