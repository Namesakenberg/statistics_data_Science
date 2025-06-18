```mermaid
flowchart TB
    %% User Interface Layer
    User["User (Browser)"]:::ui
    Jupyter["Jupyter Server"]:::runtime
    Kernel["Python Kernel"]:::runtime
    Env["Libraries<br>(pandas, NumPy, SciPy,<br>matplotlib, seaborn,<br>statsmodels)"]:::runtime

    %% Documentation
    README["README.md"]:::code

    %% Computational Flow
    User --> Jupyter
    Jupyter --> Kernel
    Kernel --> Env
    Env -->|"loads environment"| QND
    Env --> CLT
    Env --> PStat
    Env --> TT
    Env --> CS
    Env --> HT
    Env --> PCI
    Env --> CI
    Env --> BCYJ
    Env --> LOG
    Env --> VLIN
    Env --> OWA
    Env --> README

    %% Notebooks Grouped by Theme
    subgraph "Distributions & Probability" 
        direction TB
        QND["Questions_on_normal_dist.ipynb"]:::code
        CLT["Central_limit_theorem.ipynb"]:::code
        PStat["probability_and_statistics.ipynb"]:::code
    end

    subgraph "Statistical Tests"
        direction TB
        TT["Questios_on_T_tests_.ipynb"]:::code
        CS["chi_square_tests.ipynb"]:::code
        HT["hypothesis_testing_session_46_Ipynb.ipynb"]:::code
        PCI["Practice_of_Confidence_intervals_.ipynb"]:::code
        CI["Confidence_intervals_(Z,T)_.ipynb"]:::code
    end

    subgraph "Transformations & Regression Prep"
        direction TB
        BCYJ["Box_Cox_and_Yeo_Johnson_transformers_on_concrete_strength_dataset.ipynb"]:::code
        LOG["log_transformation_on_titanic_dataset.ipynb"]:::code
        VLIN["vectors__LinAlg.ipynb"]:::code
    end

    subgraph "ANOVA"
        direction TB
        OWA["One_Way_ANOVA.ipynb"]:::code
    end

    %% Data Sources
    DataCSV["Local CSVs / Built-in Datasets"]:::data

    %% Outputs
    Plots["Plots (matplotlib, seaborn)"]:::output
    Tables["Summary Tables & Markdown"]:::output

    %% Data Flow Between Layers
    DataCSV -->|"load data"| QND
    DataCSV --> CLT
    DataCSV --> PStat
    DataCSV --> TT
    DataCSV --> CS
    DataCSV --> HT
    DataCSV --> PCI
    DataCSV --> CI
    DataCSV --> BCYJ
    DataCSV --> LOG
    DataCSV --> VLIN
    DataCSV --> OWA

    QND -->|"render plot"| Plots
    CLT --> Plots
    PStat --> Plots
    TT --> Tables
    CS --> Tables
    HT --> Tables
    PCI --> Tables
    CI --> Tables
    BCYJ --> Plots
    LOG --> Plots
    VLIN --> Tables
    OWA --> Tables

    Plots -->|"display results"| User
    Tables --> User

    %% Click Events
    click QND "https://github.com/namesakenberg/statistics_data_science/blob/main/Questions_on_normal_dist.ipynb"
    click CLT "https://github.com/namesakenberg/statistics_data_science/blob/main/Central_limit_theorem.ipynb"
    click PStat "https://github.com/namesakenberg/statistics_data_science/blob/main/probability_and_statistics.ipynb"
    click TT "https://github.com/namesakenberg/statistics_data_science/blob/main/Questios_on_T_tests_.ipynb"
    click CS "https://github.com/namesakenberg/statistics_data_science/blob/main/chi_square_tests.ipynb"
    click HT "https://github.com/namesakenberg/statistics_data_science/blob/main/hypothesis_testing_session_46_Ipynb.ipynb"
    click PCI "https://github.com/namesakenberg/statistics_data_science/blob/main/Practice_of_Confidence_intervals_.ipynb"
    click CI "https://github.com/namesakenberg/statistics_data_science/blob/main/Confidence_intervals_(Z,T)_.ipynb"
    click BCYJ "https://github.com/namesakenberg/statistics_data_science/blob/main/Box_Cox_and_Yeo_Johnson_transformers_on_concrete_strength_dataset.ipynb"
    click LOG "https://github.com/namesakenberg/statistics_data_science/blob/main/log_transformation_on_titanic_dataset.ipynb"
    click VLIN "https://github.com/namesakenberg/statistics_data_science/blob/main/vectors__LinAlg.ipynb"
    click OWA "https://github.com/namesakenberg/statistics_data_science/blob/main/One_Way_ANOVA.ipynb"
    click README "https://github.com/namesakenberg/statistics_data_science/blob/main/README.md"

    %% Styles
    classDef ui fill:#e5e5e5,stroke:#333,stroke-width:1px;
    classDef runtime fill:#cce5ff,stroke:#333,stroke-width:1px;
    classDef code fill:#ccffcc,stroke:#333,stroke-width:1px;
    classDef data fill:#fff2cc,stroke:#333,stroke-width:1px;
    classDef output fill:#ffd9b3,stroke:#333,stroke-width:1px;

