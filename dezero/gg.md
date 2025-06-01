flowchart LR
  %% 왼쪽 컬럼(세로 배치)
  subgraph LEFT_COLUMN
    direction TB
    A[Data Collection]
    B[WM811K /\nWafer Test Data]
    C[Data Preprocessing]
    D[Resampling /\nNormalization /\nAugmentation]
    E[Model Training]
    F[CNN or\nWaferSegClassNet]

    A --> B
    B --> C
    C --> D
    D --> E
    E --> F
  end

  %% 오른쪽 컬럼(세로 배치)
  subgraph RIGHT_COLUMN
    direction TB
    G[Model Evaluation & Testing]
    H[Accuracy / Precision / Recall]
    I[Results Visualization & UI]
    J[PyQt UI →\nPASS/FAIL Decision]
    K[Web-Based Query →\nDB Storage]
    L[Visualization]

    G --> H
    H --> I
    I --> J
    J --> K
    K --> L
  end

  %% 왼쪽 마지막 노드에서 오른쪽 첫 노드로 연결
  F --> G

  %% 노드 스타일 지정
  classDef blackNodeStyle fill:#ffffff,stroke:#000,stroke-width:1px,color:#000000;
  class A,B,C,D,E,F,G,H,I,J,K,L blackNodeStyle;

  %% 화살표 두께 조정 (모든 링크를 3px로)
  linkStyle default stroke-width:3px
