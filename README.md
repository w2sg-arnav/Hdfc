```mermaid
flowchart TB
    subgraph DataSources["Data Sources & Ingestion"]
        direction TB
        M["Market Data<br/>- Real-time feeds<br/>- Historical data"]
        T["Transaction Data<br/>- Structured<br/>- Unstructured"]
        ETL["ETL Pipelines<br/>- Batch processing<br/>- Stream processing"]
    end

    subgraph Storage["Data Storage Layer"]
        direction TB
        DL["Data Lake<br/>- AWS S3<br/>- Azure Blob Storage"]
        DB["Databases<br/>- PostgreSQL<br/>- MongoDB"]
        FS["Feature Store<br/>- Feature engineering<br/>- Version control"]
    end

    subgraph Compute["High-Performance Computing"]
        direction TB
        KUB["Kubernetes<br/>- Container orchestration<br/>- Auto-scaling<br/>- Load balancing"]
        SPARK["Apache Spark<br/>- In-memory processing<br/>- Distributed computing"]
        GPU["GPU Computing<br/>- NVIDIA CUDA<br/>- TensorFlow acceleration"]
    end

    subgraph ML["ML/AI Pipeline"]
        direction TB
        DLM["Deep Learning<br/>- TensorFlow<br/>- PyTorch<br/>- LSTMs/Transformers"]
        RL["Portfolio Optimization<br/>- Reinforcement Learning<br/>- Genetic Algorithms<br/>- Markowitz Theory"]
        XAI["Explainable AI<br/>- SHAP<br/>- LIME"]
        MLOPS["MLOps<br/>- Kubeflow<br/>- MLflow<br/>- Model monitoring"]
    end

    subgraph Risk["Risk Management System"]
        direction TB
        RT["Real-time Monitoring<br/>- Live risk metrics<br/>- Threshold alerts"]
        ST["Risk Analysis<br/>- Stress testing<br/>- VaR calculations<br/>- Monte Carlo simulations"]
        AD["Anomaly Detection<br/>- Market behavior<br/>- Portfolio alerts"]
    end

    subgraph Security["Security Framework"]
        direction TB
        ZT["Zero Trust Security<br/>- Istio service mesh<br/>- End-to-end encryption"]
        AUTH["Authentication<br/>- OAuth 2.0<br/>- SAML"]
        COMP["Compliance<br/>- ISO 27001<br/>- PCI DSS<br/>- GDPR"]
    end

    subgraph Interface["User Interface & Integration"]
        direction TB
        API["APIs<br/>- REST endpoints<br/>- Webhooks"]
        DASH["Visualization<br/>- Power BI<br/>- Tableau<br/>- Custom dashboards"]
        INT["System Integration<br/>- Oracle<br/>- SAP<br/>- Legacy systems"]
    end

    DataSources --> Storage
    Storage --> Compute
    Compute --> ML
    ML --> Risk
    Risk --> Interface
    
    Security --> DataSources
    Security --> Storage
    Security --> Compute
    Security --> ML
    Security --> Risk
    Security --> Interface

    %% Styling
    classDef primary fill:#2196F3,stroke:#1976D2,color:white
    classDef compute fill:#4CAF50,stroke:#388E3C,color:white
    classDef security fill:#F44336,stroke:#D32F2F,color:white
    classDef ml fill:#9C27B0,stroke:#7B1FA2,color:white
    classDef interface fill:#FF9800,stroke:#F57C00,color:white

    class DataSources,Storage primary
    class Compute compute
    class Security security
    class ML ml
    class Risk,Interface interface
