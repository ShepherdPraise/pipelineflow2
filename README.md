# pipelineflow
Pipeline CI
```mermaid
graph TD
    A[Start] --> B[Push to 0-iHealth-Dev1-General/main]
    B --> C[Dev to QA Workflow]
    C --> D[Checkout Dev Repo<br>Update Submodules<br>Create QA Sync Branch<br>Commit & Push]
    D --> E[Create PR to 0-iHealth-Dev1-General-QA/main]
    E --> F[PR Merged to QA/main]
    F --> G[QA to Pre-Prod Workflow]
    G --> H[Checkout QA Repo<br>Update Submodules<br>Create Pre-Prod Sync Branch<br>Commit & Push]
    H --> I[Create PR to 0-iHealth-PreProd-General/main]
    I --> J[PR Merged to Pre-Prod/main]
    J --> K[Pre-Prod to Prod Workflow]
    K --> L[Checkout Pre-Prod Repo<br>Update Submodules<br>Create Prod Sync Branch<br>Commit & Push]
    L --> M[Create PR to 0-iHealth-Prod-General/main]
    M --> N[PR Merged to Prod/main]
    N --> O[End]
...
