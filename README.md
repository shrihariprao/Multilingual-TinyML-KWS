# Multilingual TinyML Keyword Spotting

Research prototype exploring keyword spotting across Kannada, Tamil, Telugu and Malayalam.

## Contents
- `notebooks/`: Colab notebook
- `models/`: saved model artifacts
- `data/`: available processed data
- `results/`: evaluation reports, metrics and figures

## Evaluation notes
The current prototype uses synthetic samples. The sample-level and family-disjoint evaluations differ substantially; the family-disjoint result should be considered when assessing generalization. Native-speaker validation and real-device measurements remain necessary before claiming real-world performance.

## Interactive research dashboards

Open the [dashboard hub](results/dashboards/index.html) to explore:
- [Project overview](results/dashboards/01_project_overview.html)
- [Performance by language](results/dashboards/02_language_performance.html)
- [Error analysis](results/dashboards/03_error_analysis.html)
- [Deployment readiness](results/dashboards/04_deployment_readiness.html)

These dashboards use the saved evaluation reports. Results are preliminary and based on synthetic samples; the family-disjoint evaluation is the stricter generalization check. Native-speaker validation and physical-device latency/energy measurements remain outstanding.
