graph TD
    Browser["Browser (UI)"]:::ui
    Server["Jupyter Server"]:::runtime
    Kernel["Python Kernel & Env"]:::runtime

    Browser -->|"HTTP/WebSocket"| Server
    Server -->|"ZeroMQ"| Kernel

    subgraph "Notebook Modules"
        subgraph "Descriptive Statistics & Probability Distributions"
            Prob["probability_and_statistics.ipynb"]:::code
            CLT["Central_limit_theorem.ipynb"]:::code
            Q1["Questions_on_stats_1.ipynb"]:::code
            Q2["Questions_on_normal_dist.ipynb"]:::code
        end
        subgraph "Inferential Statistics & Hypothesis Testing"
            CI["Confidence_intervals_(Z,T)_.ipynb"]:::code
            PCI["Practice_of_Confidence_intervals_.ipynb"]:::code
            ANOVA["One_Way_ANOVA.ipynb"]:::code
            CS["chi_square_tests.ipynb"]:::code
            QT["Questios_on_T_tests_.ipynb"]:::code
            HT["hypothesis_testing_session_46_Ipynb.ipynb"]:::code
        end
        subgraph "Data Transformations"
            BC["Box_Cox_and_Yeo_Johnson_transformers_on_concrete_strength_dataset.ipynb"]:::code
            LOG["log_transformation_on_titanic_dataset.ipynb"]:::code
        end
        subgraph "Linear Algebra (Vectors)"
            VEC["vectors__LinAlg.ipynb"]:::code
        end
    end

    Kernel -->|"loads notebooks"| Prob
    Kernel -->|"loads notebooks"| CI
    Kernel -->|"loads notebooks"| BC
    Kernel -->|"loads notebooks"| VEC

    DataSources["Data Sources"]:::data
    Kernel -->|"reads CSV/datasets"| DataSources

    subgraph "Core Libraries"
        Num["NumPy"]:::deps
        Pand["pandas"]:::deps
        Sci["SciPy"]:::deps
        Mpl["Matplotlib/Seaborn"]:::deps
        Sk["scikit-learn"]:::deps
    end

    Kernel -->|"calls APIs"| Num
    Kernel --> Pand
    Kernel --> Sci
    Kernel --> Mpl
    Kernel --> Sk

    README["README.md"]:::code
    README -.-> Browser
    README -.-> Kernel

    click Prob "https://github.com/namesakenberg/statistics_data_science/blob/main/probability_and_statistics.ipynb"
    click CLT "https://github.com/namesakenberg/statistics_data_science/blob/main/Central_limit_theorem.ipynb"
    click Q1 "https://github.com/namesakenberg/statistics_data_science/blob/main/Questions_on_stats_1.ipynb"
    click Q2 "https://github.com/namesakenberg/statistics_data_science/blob/main/Questions_on_normal_dist.ipynb"
    click CI "https://github.com/namesakenberg/statistics_data_science/blob/main/Confidence_intervals_(Z,T)_.ipynb"
    click PCI "https://github.com/namesakenberg/statistics_data_science/blob/main/Practice_of_Confidence_intervals_.ipynb"
    click ANOVA "https://github.com/namesakenberg/statistics_data_science/blob/main/One_Way_ANOVA.ipynb"
    click CS "https://github.com/namesakenberg/statistics_data_science/blob/main/chi_square_tests.ipynb"
    click QT "https://github.com/namesakenberg/statistics_data_science/blob/main/Questios_on_T_tests_.ipynb"
    click HT "https://github.com/namesakenberg/statistics_data_science/blob/main/hypothesis_testing_session_46_Ipynb.ipynb"
    click BC "https://github.com/namesakenberg/statistics_data_science/blob/main/Box_Cox_and_Yeo_Johnson_transformers_on_concrete_strength_dataset.ipynb"
    click LOG "https://github.com/namesakenberg/statistics_data_science/blob/main/log_transformation_on_titanic_dataset.ipynb"
    click VEC "https://github.com/namesakenberg/statistics_data_science/blob/main/vectors__LinAlg.ipynb"
    click README "https://github.com/namesakenberg/statistics_data_science/blob/main/README.md"

    classDef ui fill:#B0E0E6,stroke:#000,stroke-width:1px;
    classDef runtime fill:#ADD8E6,stroke:#000,stroke-width:1px;
    classDef code fill:#98FB98,stroke:#000,stroke-width:1px;
    classDef data fill:#FFA500,stroke:#000,stroke-width:1px;
    classDef deps fill:#D3D3D3,stroke:#000,stroke-width:1px;
