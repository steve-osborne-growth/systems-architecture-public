# Data Flow

This diagram shows how data moves through Project Crosstalk from source to final output.

```mermaid
flowchart TD
    A([Keyword Input]) --> B[Environment Setup]
    C([Gong API]) --> D[Ingestion Layer]
    E([Salesforce API]) --> D

    B --> D
    D --> F[Internal Speaker Filter]
    F --> G[Keyword Scanner]
    G --> H[Snippet Extractor\n10 sentences before and after each match]

    H --> I[Snippet Pool]

    I --> J[Pass 1: Extraction\nWhat is the customer saying?]
    J --> K[Pass 2: Synthesis\nWhat patterns emerge across snippets?]
    K --> L[Pass 3: Audit\nCheck for bias and internal voice contamination]
    L --> M[Pass 4: Packaging\nFormat findings for stakeholder output]

    M --> N{Output Format}
    N --> O([Excel Report])
    N --> P([Google Sheets])
    N --> Q([PDF Report])

    style A fill:#dbeafe,stroke:#93c5fd,color:#1e3a5f
    style C fill:#dbeafe,stroke:#93c5fd,color:#1e3a5f
    style E fill:#dbeafe,stroke:#93c5fd,color:#1e3a5f
    style O fill:#dcfce7,stroke:#86efac,color:#14532d
    style P fill:#dcfce7,stroke:#86efac,color:#14532d
    style Q fill:#dcfce7,stroke:#86efac,color:#14532d
    style I fill:#fef9c3,stroke:#fde047,color:#713f12
```

---

## Stage Descriptions

**Environment Setup**
Installs required libraries, mounts Google Drive, and loads API credentials. This runs before any data is touched to ensure the system has everything it needs.

**Ingestion Layer**
Connects to the Gong API to pull call transcripts and metadata. Connects to the Salesforce API to pull firmographic and opportunity data. Both are combined into a unified record per customer interaction.

**Internal Speaker Filter**
Removes all turns from internal Trimble speakers. Only customer voice passes through to the next stage.

**Keyword Scanner**
Scans each transcript for predefined keywords, competitor names, product mentions, and thematic concepts. Flags each match with its location in the transcript.

**Snippet Extractor**
For each flagged match, extracts a context window of approximately 10 sentences before and after. These snippets are what the AI actually reads. Full transcripts are never passed to the model.

**Snippet Pool**
The collection of all extracted snippets for a given analysis run. Snippets can be grouped per call or aggregated per customer depending on the analysis type. This is the only input to the AI pipeline.

**AI Analysis Pipeline (4 passes)**
Each pass has a specific, scoped job. Outputs from one pass feed into the next. This structure reduces hallucination and improves consistency across large volumes of input.

**Output Layer**
Final packaged findings are delivered as an Excel file with formatted headers and hyperlinks back to the source calls, a Google Sheets file for interactive filtering, or a PDF depending on the use case and stakeholder.

---

[Back to Project Crosstalk](../README.md)
