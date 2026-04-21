# Data Flow

This diagram shows how data moves through Project Higgs from raw sources to board-ready deliverables.

```mermaid
flowchart TD
    A([Domo\nFirmographic Data]) --> E[Data Ingestion]
    B([Gong API\nCall Transcripts]) --> E
    C([Salesforce API\nDeal Data]) --> E
    D([Google Forms\nSeller & Leader Input]) --> E

    E --> F[Data Normalization\nPython in Google Colab]

    F --> G[Temporary\nNormalized Dataset]

    G --> H[Deal Analysis Path]
    G --> I[Customer Evidence Path]

    H --> J[AI Pass 1: Extract\nAtomic Findings per Deal]
    J --> K[AI Pass 2: So What\nAnalysis & Context]
    K --> L[AI Pass 3: Bias &\nSkeptic Review]
    L --> M[Human-in-the-Loop\nLeader Review]

    I --> N[Crosstalk Snippet\nExtraction Engine]
    N --> O[AI Analysis: Customer\nQuotes on Connect & Scale]
    O --> P[Filter: External\nVoice Only]
    P --> Q[Categorize by Product\nVertical, Title]

    M --> R[Final Assembly\nNarrative Blocks]
    Q --> R

    R --> S{Output Format}
    S --> T([PDF Report])
    S --> U([Google Doc])
    S --> V([Google Sheets])

    style A fill:#dbeafe,stroke:#93c5fd,color:#1e3a5f
    style B fill:#dbeafe,stroke:#93c5fd,color:#1e3a5f
    style C fill:#dbeafe,stroke:#93c5fd,color:#1e3a5f
    style D fill:#dbeafe,stroke:#93c5fd,color:#1e3a5f
    style T fill:#dcfce7,stroke:#86efac,color:#14532d
    style U fill:#dcfce7,stroke:#86efac,color:#14532d
    style V fill:#dcfce7,stroke:#86efac,color:#14532d
    style G fill:#fef9c3,stroke:#fde047,color:#713f12
```

---

## Stage Descriptions

**Data Ingestion**
Pulls from four sources: Domo for firmographic and financial data, the Gong API for call transcripts, the Salesforce API for deal records and pipeline data, and Google Forms for qualitative input from sellers and leadership.

**Data Normalization**
All inputs are transformed and normalized in Python running in Google Colab. The result is a single temporary dataset that can be branched into different analysis paths.

**Deal Analysis Path**
Individual deals are run through a multi-pass AI pipeline. Pass 1 extracts atomic findings from each deal. Pass 2 generates "so what" context explaining why the deal matters. Pass 3 reviews for bias and skepticism to ensure the analysis is balanced. Leaders then review the output before it is finalized.

**Customer Evidence Path**
Uses the Crosstalk snippet extraction engine to scan across the full transcript database for customer mentions of customer adoption initiatives. Internal speakers are filtered out. Results are categorized by product, customer vertical, and speaker title.

**Final Assembly**
Both paths feed into a final assembly step where AI drafts narrative blocks for each section of the board material. These blocks are combined into the final deliverable in the requested format.

---

[Back to Project Higgs](../README.md)
