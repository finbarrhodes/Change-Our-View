# Change Our View: A Distributed Topic Modelling and Feature-Based Study of Persuasion Dynamics in r/ChangeMyView

![License](https://img.shields.io/badge/license-MIT-blue.svg)

## Overview

This repository contains the code, analysis, and results for the "Change Our View" project, which explores the mechanics of opinion change in the r/ChangeMyView subreddit by combining large-scale text mining with distributed machine-learning pipelines. The project leverages PySpark and distributed computing techniques to process 65,169 discussion threads from the Webis-CMV-20 corpus.

## Key Research Questions

1. What drives users to concede their views in online discussions?
2. Can we predict opinion change based on how users approach online discussions?
3. How do structural, linguistic, sentiment, and temporal features correlate with persuasion?

## Key Contributions

- A cleaned CMV corpus of 65,169 original posts
- A 45-topic Spark LDA model fitted to the entire corpus and manually mapped to 14 semantic categories
- An interpretable feature set that describes how original posters (OPs) approach discussion forums
- Additional features including sentiment analysis and time series comparisons across topics
- A comparison between single-core and multi-core decision trees demonstrating scaling advantages

## Repository Structure

```
├── Notebooks/
│   ├── 1_DataAcquisition_Preprocessing.ipynb
│   ├── 2_TopicModelling.ipynb
│   ├── 3_FeatureEngineering.ipynb
│   ├── 4_PredictiveModels.ipynb
│   └── 5_DistributedLearning.ipynb
├── Misc/
│   ├── PROPOSAL.md
│   ├── my_actions.sh
│   └── AI_Chat_Logs.pdf
├── README.md
└── Change_Our_View_Report.pdf
```

## Key Findings

- Post length, interaction volume, and readability signal a higher likelihood of concession, rather than the topic or sentiment behind the post
- Our best distributed model attains an F1 score of 0.64 while scaling linearly across a 12-node Spark cluster
- The distributed approach reduces the random-forest training time from 49s to under 7s
- Community interaction patterns are strongly correlated with persuasion, rather than thematic content

## Methodology

1. **Data Acquisition & Pre-processing**: Cleaned and merged post metadata from the Webis-CMV-20 corpus
2. **Topic Modelling**: Implemented distributed Latent Dirichlet Allocation (LDA) with 45 topics mapped to 14 semantic categories
3. **Feature Engineering**: Created interpretable features capturing post structure, linguistics, sentiment, and engagement
4. **Predictive Models**: Trained both standard and distributed models (Logistic Regression, Random Forest, Distributed Decision Trees)
5. **Scalability Analysis**: Compared performance and efficiency of single-core vs. distributed implementations

## Requirements

- Apache Spark 3.5
- PySpark
- NLTK with VADER lexicon
- Google Cloud Platform (GCP) environment (for distributed execution)
- A 12-node Dataproc cluster running Spark

## Usage

The notebooks should be run in sequential order (1 through 5). Each notebook produces output artifacts that are used by subsequent notebooks.

Example for running in a distributed environment:
```bash
# Run the custom shell script to install dependencies
./Misc/my_actions.sh

# Execute notebooks in sequence on the Dataproc cluster
```

## Future Work

Potential areas for future research:
- Incorporating network effects and user history into prediction models
- Using transformer-based embeddings for more sophisticated NLP
- Longitudinal analysis to track how persuasion dynamics evolve over time
- Expanding to other subreddits for comparative analysis

## Citation

If you use this code or the findings in your research, please cite:
```
@misc{changeourview2025,
  author = {39375, 41830, 44051, 42309},
  title = {Change Our View: A Distributed Topic Modelling and Feature-Based Study of Persuasion Dynamics in r/ChangeMyView},
  year = {2025},
  publisher = {GitHub},
  url = {https://github.com/yourusername/ChangeOurView}
}
```

## License

This project is licensed under the MIT License - see the LICENSE file for details.
