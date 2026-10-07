# Awesome-Machine-Learning-Platform

# Top Machine Learning Platform Ecosystem

**Curated List of SaaS Products & Open-Source GitHub Projects**  
*Focused on End-to-End MLOps, Model Serving & Self-Hosted ML Infrastructure*  
**Last updated: October 2026**

This repository tracks notable **commercial machine learning platforms** and **open-source projects** that cover the full ML lifecycle — from data preparation and experiment tracking to model deployment, monitoring, and governance — without vendor lock-in.

**Examples** include Amazon SageMaker, Google Cloud Vertex AI, Microsoft Azure Machine Learning, Databricks Machine Learning, DataRobot AI Platform, Domino Data Lab, H2O AI Cloud, Dataiku DSS, Paperspace Gradient, and Saturn Cloud (the category leaders).

**Open-source emphasis**: Machine learning platforms are one of the strongest open-source domains. **Kubeflow** recently graduated from CNCF, solidifying its status as the standard for cloud-native AI operations . **MLflow** remains the de facto experiment tracking and model registry standard. **Feast** leads as the open-source feature store . **MLOX** brings lightweight, backend-agnostic MLOps orchestration . **ZebraOps** delivers local-first MLOps for small teams . **Potato** and **AnyLabeling** handle data annotation . **P-ML** and **ModelForge** provide AutoML . This section is heavily expanded.

Contributions welcome! Open a PR to add/update entries. Keep descriptions factual and link to official sites.

## Table of Contents
- [SaaS/Hosted Platforms](#saas-hosted-platforms)
- [Open-Source GitHub Projects](#open-source-github-projects)
- [How to Contribute](#how-to-contribute)
- [Disclaimer](#disclaimer)

## SaaS/Hosted Platforms

- **[Amazon SageMaker](https://aws.amazon.com/sagemaker/)**  
  **AWS's fully managed ML platform** — the widest feature set covering data labeling, training, tuning, deployment, and monitoring . **Deep AWS integration** with IAM, VPC, and Fargate . **Trade-off**: Highly fragmented pricing model — training, hosting, pipelines, and feature stores are billed separately, making costs unpredictable without strict FinOps governance  . **Best for AWS-native organizations with dedicated ML platform teams** .

- **[Google Cloud Vertex AI](https://cloud.google.com/vertex-ai)**  
  **Google's unified ML platform** — deeply integrated with BigQuery and Google's data stack . **Cleaner pricing model with Committed Use Discounts (CUDs)** that apply across the platform  . **AutoML and custom training** with strong MLOps capabilities . **Best for data-heavy organizations already invested in Google Cloud** .

- **[Microsoft Azure Machine Learning](https://azure.microsoft.com/en-us/products/machine-learning/)**  
  **Microsoft's enterprise ML platform** — the default choice for Azure-first organizations . **Leverages existing Enterprise Agreements and Azure Hybrid Benefit for compute**  . **Integration with Azure OpenAI is the primary differentiator** . **Best for Microsoft-centric enterprises** .

- **[Databricks Machine Learning](https://www.databricks.com/)**  
  **Unified data and AI platform** — lakehouse architecture with MLflow integration . **Best for organizations using Spark and Delta Lake** .

- **[DataRobot AI Platform](https://www.datarobot.com/)**  
  **Enterprise AutoML and AI platform** — automated model building, deployment, and governance . **Best for enterprises wanting automated ML without deep data science teams** .

- **[Domino Data Lab](https://www.dominodatalab.com/)**  
  **Enterprise MLOps platform** — reproducible research, model deployment, and governance . **Best for regulated industries** .

- **[H2O AI Cloud](https://h2o.ai/)**  
  **Enterprise AI platform** — AutoML, feature store, and model deployment . **Best for enterprises wanting open-core AI infrastructure** .

- **[Dataiku DSS](https://www.dataiku.com/)**  
  **Collaborative data science platform** — visual ML, data preparation, and deployment . **Best for teams wanting visual and code-based workflows** .

- **[Paperspace Gradient](https://www.paperspace.com/)**  
  **Cloud ML platform** — GPU-powered notebooks and training workflows . **Best for individual developers and small teams** .

- **[Saturn Cloud](https://saturncloud.io/)**  
  **Cloud platform for data science and ML** — Dask and GPU support . **Best for parallel computing workloads** .

## Open-Source GitHub Projects

### End-to-End MLOps Platforms

- **[Kubeflow](https://github.com/kubeflow/kubeflow)**  
  **The CNCF-graduated standard for cloud-native AI operations**, Apache-2.0 licensed with **15,000+ GitHub stars**  . **Provides the entire data & AI lifecycle** — Kubeflow Pipelines for workflow orchestration, Katib for hyperparameter tuning, Training Operator for distributed training (PyTorch, TensorFlow, MPI, XGBoost), and KServe for model serving . **Completed a third-party security audit** and maintains CII Best Practices Badge  . **Used by Capital One, DHL, and organizations worldwide**  . **Best for Kubernetes-native ML platforms** .

- **[MLOX](https://github.com/matteospanio/mlox)**  
  **Open-source MLOps for the rest of us**, open-source  . **Backend-agnostic** — same service definitions target Docker, Kubernetes, Native, or Connector backends . **Lightweight and minimal operational overhead** — reuses existing hardware and reduces resource consumption . **Service-centric orchestration** — users select services (MLflow, Airflow, OpenBao, Registry3) through CLI, TUI, or Web UI . **Declarative and idempotent** — infrastructure-as-code discipline without manual configuration . **Best for small teams and experimentation**  .

- **[ZebraOps](https://github.com/flexiana/zebraops)**  
  **Local-first, open-source MLOps platform for ML beginners and small teams**, Apache-2.0 licensed  . **Full lifecycle CLI** — init, ingest, train, eval, promote, serve, monitor . **Contract-first model specs and immutable dataset manifests** . **Integrated stack**: MLflow for tracking, Prefect for orchestration, FastAPI for serving, Evidently for drift monitoring, Docker Compose for local devstack (Postgres, MinIO, Grafana, Prometheus) . **Profile adapters for Vast, SageMaker, Vertex** . **Best for local-first MLOps**  .

- **[LUML](https://app.luml.ai/)**  
  **Open-source MLOps and LLMOps platform where engineers and AI agents work side by side**, open-source  . **Prisma agent module** — AutoResearch-style AI agents that autonomously design, iterate on, and build ML solutions . **Flow** — real-time experiment tracking for classical ML runs alongside LLM traces and evaluations . **Core** — model and artifact registry with full lineage, one-click deployments, and monitoring . **Best for agent-assisted ML development**  .

### Experiment Tracking & Model Registry

- **[MLflow](https://github.com/mlflow/mlflow)**  
  **The de facto standard for ML lifecycle management**, Apache-2.0 licensed with **20,000+ GitHub stars** . **Experiment tracking, model registry, projects, and recipes** . **Works with any ML library and language** . **The foundation for ZebraOps and many other platforms**  . **Best for experiment tracking and model registry** .

- **[mlsolid](https://pkg.go.dev/github.com/zeddo123/mlsolid)**  
  **A solid alternative to MLflow, written in Go with Redis and S3**, open-source  . **Fast** — Redis-backed metadata with sorted-set indexes for stable cursor-based pagination at scale . **Production focused and easy to deploy** — single Go binary plus Redis and S3-compatible bucket, no JVM/Python server stack . **Dumb client** — client only sends experiments, metrics, and artifacts; no business logic to keep in sync . **Model registry with versioning** — register models per run, tag versions, stream back efficiently over gRPC . **Automated benchmarking** — attach Docker image to registry; new model versions run against dataset automatically . **Best-model selection** — query top run across benchmark by metrics . **Polyglot clients** — gRPC SDKs generated for multiple languages . **Best for production-grade experiment tracking**  .

- **[vmn-exp](https://pypi.org/project/vmn-exp/)**  
  **Experiment platform built on vmn**, open-source  . **Experiment tracking, model registry, snapshots, and web dashboard** . **Capturing runs from a git checkout** . **Lightweight Python package** . **Best for simple experiment tracking**  .

### Feature Stores

- **[Feast](https://github.com/feast-dev/feast)**  
  **The leading open-source feature store**, Apache-2.0 licensed  . **Makes features consistently available for training and serving** — manages offline store (historical data for batch scoring/model training), low-latency online store (real-time prediction), and feature server (serve pre-computed features online) . **Avoids data leakage** — generates point-in-time correct feature sets so future feature values don't leak to models during training . **Decouples ML from data infrastructure** — single data access layer abstracts feature storage from retrieval, ensuring models remain portable across training/serving and batch/real-time . **Supports Kafka, Kinesis, Snowflake, BigQuery, S3, Redshift, GCS, Parquet** . **Best for production ML feature management**  .

### AutoML & Model Optimization

- **[P-ML](https://github.com/HuuPhuoc2411/P-ML)**  
  **End-to-end AutoML framework for deploying classical ML models on resource-constrained devices**, open-source  . **Automates data splitting, model selection, hyperparameter optimization, and generation of optimized Arduino-compatible C++ libraries** . **Integrates Optuna-based hyperparameter tuning with stratified data splitting (SPXY, K-Fold)** . **Achieves over 90% accuracy on sensor data classification while maintaining small memory footprint** . **Directly deployable on Arduino Uno, Nano, and ESP32** . **Best for embedded IoT ML**  .

- **[ModelForge](https://pypi.org/project/autoforge-engine/)**  
  **Transparent, local-first AutoML experimentation for reproducible and inspectable ML**, open-source  . **Regression and classification workflows** — data profiling, column intelligence, data-quality auditing, preprocessing, feature engineering, feature selection . **Model screening, cross-validation, and ranking** . **Saved model pipelines and predictions from CLI or Python** . **Local experiment tracking, run metadata, and reproducibility information** . **Optional boosting models (XGBoost, LightGBM, CatBoost) and hyperparameter optimization (Optuna)** . **Best for local-first AutoML**  .

- **[NiaAML](https://pypi.org/project/NiaAML/)**  
  **Python automated machine learning framework**, MIT licensed  . **PipelineOptimizer** — run optimization for classification and regression tasks . **Feature transform algorithms**: Normalizer, StandardScaler, MaxAbsScaler, QuantileTransformer, RobustScaler . **Feature selection algorithms**: SelectKBest, SelectPercentile, SelectUnivariateRegression . **Models**: LinearRegression, RidgeRegression, LassoRegression, DecisionTreeRegression, GaussianProcessRegression . **Export and load pipelines** . **Best for research and custom AutoML**  .

### Data Annotation & Labeling

- **[Potato 2.0](https://aclanthology.org/2026.acl-demo.37/)**  
  **Comprehensive annotation platform with AI-in-the-loop support**, open-source, published at ACL 2026  . **39 different annotation task types** with support for text, audio, image, and video modalities . **Robust support for labeling agentic system outputs** — reading common trace formats, live interaction and annotation with agents (chatting, web-browsing, coding) . **AI-assistance features** to help annotators label data more easily . **Agentic AI-in-the-loop workflow** — single human annotator collaborates with LLM through iterative prompt refinement, uncertainty-driven instance selection, and progressive autonomy . **Best for NLP and multimodal data annotation**  .

- **[AnyLabeling](https://pypi.org/project/anylabeling-gpu/)**  
  **Effortless data labeling with AI support from YOLO and Segment Anything**, open-source  . **Image annotation for polygon, rectangle, circle, line, and point** . **Auto-labeling with YOLOv8 (object detection)** . **Auto-labeling with Segment Anything family**: SAM (ViT-B/L/H), MobileSAM, SAM 2/2.1 (Hiera-Tiny/Small/Base+/Large), and **SAM 3 (ViT-H) for open-vocabulary segmentation with text prompts** . **Text detection, recognition, and KIE labeling** . **Multiple languages available** . **Best for computer vision data labeling**  .

- **[visionset](https://pypi.org/project/visionset/)**  
  **Computer vision dataset management and annotation platform**, open-source  . **CLI-driven workflow**: project create, schema apply, ingest, batch approve, annotate, batch complete, release publish, export . **Export to YOLO, COCO, VOC, classification, and lane formats** . **REST API with OpenAPI contract** . **MCP server with 56 agent tools** for AI-assisted annotation . **Hash-verified releases with train/val/test splits** . **Best for production CV dataset pipelines**  .

### Additional Strong Open-Source Options

- **Apache Airflow** — Workflow orchestration for ML pipelines .
- **Prefect** — Python-native workflow orchestration .
- **Dagster** — Data orchestration with asset graph .
- **DVC** — Data version control for ML projects .
- **Weights & Biases** — Experiment tracking and visualization (commercial with free tier) .
- **Optuna** — Hyperparameter optimization framework .
- **Ray** — Distributed computing for ML training and serving .
- **BentoML** — Unified model serving framework .
- **KServe** — Kubernetes-native model serving .
- **Evidently** — ML model monitoring and drift detection .

**Frameworks for building custom ML platform solutions**: Combine **Kubeflow** for Kubernetes-native end-to-end ML lifecycle  . Use **MLflow** or **mlsolid** for experiment tracking and model registry  . Deploy **Feast** for feature store management  . Integrate **MLOX** or **ZebraOps** for lightweight MLOps orchestration  . Use **Potato** or **AnyLabeling** for data annotation  . Choose **P-ML** or **ModelForge** for AutoML  . Note that true enterprise ML platforms with managed infrastructure, automatic scaling, and vendor-supported SLAs (SageMaker, Vertex AI, Azure ML) remain primarily commercial territory; open-source stacks provide strong MLOps, feature store, and AutoML foundations that require integration for complete ML platform deployments.

## How to Contribute

1. Fork the repo.
2. Add/edit entries in `README.md` (follow existing format).
3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.
4. Submit PR with a short explanation.

Star the repo if you find it useful!

## Disclaimer

- This is a **community-curated** list — not exhaustive and not an endorsement.
- Machine learning platforms handle sensitive data and model artifacts. Self-hosted solutions require proper security hardening, access controls, and compliance with data privacy regulations.
- **Total cost of ownership varies significantly** — SageMaker has unpredictable costs due to fragmented pricing, Vertex AI offers cleaner pricing with CUDs, and Azure ML leverages existing Enterprise Agreements  . The most expensive platform is the one your team doesn't know how to optimize  .
- **License considerations**: Kubeflow uses Apache-2.0, MLflow uses Apache-2.0, Feast uses Apache-2.0, ZebraOps uses Apache-2.0, and mlsolid is open-source . Verify licensing against your use case before committing.
- The open-source ecosystem provides strong MLOps, feature store, and AutoML foundations, but **managed infrastructure, automatic scaling, and vendor-supported SLAs** remain primarily commercial offerings.

---

**Made for ML engineers, data scientists, and organizations seeking ML platform sovereignty.**  
Let's make machine learning platforms more open, transparent, and vendor-neutral.
