flowchart TD
    A[User Clicks API Button] --> B[Fake API Server Handles Request]
    B --> C[Simulated Latency & Status Generated]
    C --> D[Monitoring Middleware Captures Data]
    D --> E[Store Log in MetricsStore]
    E --> F[Update UI Components]
    
    F --> F1[Real-time Logs (with color coding)]
    F --> F2[Metrics Panel (Req count, latency, error rate)]
    F --> F3[Requests/Latency Charts via Chart.js]

    E --> G[Trigger AI Analyzer]
    G --> H[Analyze Trends in Latency & Errors]
    H --> I[Generate Insights if thresholds breached]
    I --> J[Display Insight in UI Panel]

    subgraph Auto-Traffic
        AT1[User Clicks Auto Traffic Button]
        AT1 --> AT2[Simulate Repeated API Requests]
        AT2 --> A
    end
