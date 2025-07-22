```mermaid
graph TD
    subgraph "Client-Side"
        A[API Client Simulation] -- "1. User triggers API call" --> B(Monitoring Middleware);
    end

    subgraph "Backend (Simulated)"
        B -- "2. Starts timer & calls server" --> C{Fake API Server};
        C -- "3. Returns response (200/503)" --> B;
        B -- "4. Stops timer, calculates latency" --> D[Log Entry Created];
        D -- "5. Store metrics" --> E[(Simulated Redis Store)];
    end

    subgraph "Dashboard & Analysis"
        D -- "6. Push update via simulated WebSocket" --> F[Observability Dashboard];
        F --> G[Update KPIs & Live Log];
        F --> H[Update Charts];
        E -- "7. AI Engine pulls data periodically" --> I(💡 AI Analyzer);
        I -- "8. Anomaly detected?" --> J{Generate Insight / Alert};
        J -- "9. Display on dashboard" --> F;
    end

    style A fill:#222,stroke:#c026d3,stroke-width:2px
    style F fill:#222,stroke:#c026d3,stroke-width:2px
    style I fill:#222,stroke:#f59e0b,stroke-width:2px
