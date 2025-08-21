## Git Branching Strategy (Git Flow)

```mermaid
flowchart TD
    A([Start]) --> B[Clone Repo - main]
    B --> C[Create Feature Branch: feature/name]
    C --> D[Develop & Commit Code]
    D --> E[Push Feature Branch]
    E --> F[Pull Request to develop]
    F --> G{Code Review}

    G -->|Approved| H[Merge Feature → develop]
    G -->|Changes Requested| D

    H --> I[CI Build on develop]
    I --> J[Create Release Branch: release/x.y.z]
    J --> K[Bug Fixes & Testing]
    K --> L[Merge Release → main & Tag]
    L --> M[Merge Release → develop]

    M --> N{Hotfix Needed?}
    N -->|Yes| O[Create Hotfix Branch: hotfix/x.y.z]
    O --> P[Apply Fix]
    P --> Q[Merge Hotfix → main & Tag]
    Q --> R[Merge Hotfix → develop]
    R --> S[End]

    N -->|No| S
