# Dashboard Suite

Interactive research dashboards for the Multilingual TinyML Keyword Spotting prototype.

## Dashboards
- [Master dashboard hub](dashboards/index.html)
- [Project overview](dashboards/01_project_overview.html)
- [Performance by language](dashboards/02_language_performance.html)
- [Error analysis](dashboards/03_error_analysis.html)
- [Deployment readiness](dashboards/04_deployment_readiness.html)

The separate [interactive research dashboard](interactive_research_dashboard.html) provides a summary view.

## Interpretation and limitations
The prototype uses synthetic samples. The sample-level split may overestimate generalization because related variants crossed splits. Treat the family-disjoint evaluation as a stricter stress test, and do not claim production-ready multilingual performance without native-speaker validation and real-device evaluation.

Physical-device latency and energy consumption have not been measured. These reports are generated from saved evaluation outputs and do not retrain the model.
