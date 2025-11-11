# LastFM Asia Social Network Analysis

A comprehensive social network analysis of Last.fm users from Asian countries, exploring community structures, network dynamics, and user behavior patterns through graph analytics.

## Overview

This project performs an in-depth analysis of a social network comprising 7,624 Last.fm users and 27,806 mutual follower relationships collected via the Last.fm public API in March 2020. The analysis uncovers community structures, identifies influential users, and examines the structural properties of online music communities.

## Key Features

- **Community Detection**: Identification of 45 distinct communities using Greedy Modularity optimization
- **Network Metrics**: Comprehensive analysis of density, transitivity, and degree distribution
- **Centrality Analysis**: Betweenness centrality calculations to identify key network influencers
- **Visual Analytics**: Network visualizations highlighting community structures and node importance
- **Feature-Rich Nodes**: Integration of user music preferences (liked artists) as node attributes

## Dataset

### Source
Last.fm Asia social network dataset collected from the public API (March 2020).

### Statistics
- **Nodes**: 7,624 Last.fm users from Asian countries
- **Edges**: 27,806 mutual follower relationships
- **Density**: 0.0009 (sparse network)
- **Transitivity**: 0.1787 (moderate clustering)

### Structure
- `lastfm_asia_edges.csv`: Network edge list (mutual follows)
- `lastfm_asia_target.csv`: User locations (multinomial node classification task)
- `lastfm_asia_features.json`: User features based on liked artists

### Citation
```bibtex
@misc{rozemberczki2020characteristic,
      title={Characteristic Functions on Graphs: Birds of a Feather, from Statistical Descriptors to Parametric Models},
      author={Benedek Rozemberczki and Rik Sarkar},
      year={2020},
      eprint={2005.07959},
      archivePrefix={arXiv},
      primaryClass={cs.LG}
}
```

**FEATHER Paper**: https://arxiv.org/abs/2005.07959
**FEATHER Project**: https://github.com/benedekrozemberczki/FEATHER

## Repository Structure

```
lastfm-social-network-analysis/
├── data/
│   ├── lastfm_asia_edges.csv          # Network edges (mutual follows)
│   ├── lastfm_asia_target.csv         # User locations
│   ├── lastfm_asia_features.json      # User music preferences
│   └── README.txt                     # Dataset documentation
├── social_network_analysis.ipynb      # Main analysis notebook
├── .gitignore
└── README.md
```

## Analysis Components

### 1. Network Fundamentals
- Load and preprocess Last.fm social network data
- Calculate basic network statistics (nodes, edges, density, transitivity)
- Analyze node features and their distributions

### 2. Community Detection
- **Algorithm**: Greedy Modularity Maximization
- **Result**: 45 communities identified
- **Largest Communities**: 1,519 | 1,427 | 1,043 | 985 | 721 users
- **Visualization**: Color-coded community structure plots

### 3. Degree Distribution Analysis
- Examination of node degree sequences
- Identification of highly connected users (hubs)
- Distribution visualization to understand network topology

### 4. Centrality Analysis
- **Metric**: Betweenness centrality
- **Purpose**: Identify users who act as bridges between communities
- **Application**: Understanding information flow and influential users
- **Output**: Average centrality per community

### 5. Visualization
- Full network visualization with community color coding
- Top 10 largest communities highlighted
- Degree distribution histogram
- Spring layout with optimized parameters for clarity

## Key Findings

1. **Sparse but Connected**: Despite low density (0.0009), the network exhibits moderate clustering (transitivity: 0.1787)

2. **Community Structure**: 45 distinct communities with high modularity, indicating strong taste-based clustering among users

3. **Scale Distribution**: The largest community contains 1,519 users (~20% of network), suggesting a dominant music preference cluster

4. **Bridge Users**: Betweenness centrality analysis reveals users who connect different music taste communities

5. **Network Topology**: Degree distribution shows typical social network patterns with few highly connected hubs

## Setup & Installation

### Prerequisites
```bash
pip install networkx matplotlib numpy pandas scipy
```

### Required Libraries
- `networkx`: Graph construction and analysis
- `matplotlib`: Visualizations
- `numpy`: Numerical computations
- `pandas`: Data manipulation
- `scipy`: Statistical analysis and distance metrics

### Running the Analysis
1. Clone the repository
2. Ensure the `data/` folder contains the Last.fm dataset files
3. Open `social_network_analysis.ipynb` in Jupyter Notebook/Lab
4. Run cells sequentially to reproduce the analysis

```bash
jupyter notebook social_network_analysis.ipynb
```

## Technical Highlights

### Community Detection Algorithm
- **Method**: Greedy Modularity Communities (NetworkX implementation)
- **Complexity**: O(m * d * log(n)) where m = edges, n = nodes, d = depth
- **Advantage**: Fast and effective for large networks

### Centrality Calculation
- **Betweenness Centrality**: Measures the extent to which a node lies on paths between other nodes
- **Interpretation**: High betweenness = important connector/broker in the network
- **Application**: Identifying influencers and information bottlenecks

### Visualization Strategy
- **Spring Layout**: Force-directed graph drawing for organic community visibility
- **Color Mapping**: Rainbow color scheme for distinguishing communities
- **Performance Optimization**: Top-10 community filtering for clarity in dense networks

## Use Cases

This analysis methodology can be applied to:
- **Music Recommendation Systems**: Identify similar users for collaborative filtering
- **Marketing Strategies**: Target influential users (high centrality) for product promotion
- **Community Management**: Understand subgroup structures for content moderation
- **Network Evolution**: Track how communities form and dissolve over time
- **Cross-Cultural Analysis**: Compare network structures across different regional clusters

## Future Enhancements

- **Temporal Analysis**: Track network evolution over time
- **Predictive Modeling**: Multinomial classification for user location prediction
- **Feature Engineering**: Leverage artist preference features for community profiling
- **Advanced Algorithms**: Compare with Louvain, Label Propagation, and Infomap methods
- **Semantic Analysis**: Cluster communities by music genre preferences
- **Influence Modeling**: Cascade effects and information diffusion patterns

## Author

**Usama Ali**
[GitHub](https://github.com/aaliusama) | [LinkedIn](https://linkedin.com/in/aaliusama)

## License

This project is open source and available for educational and research purposes.

---

*This analysis demonstrates advanced graph analytics techniques for understanding social network dynamics in online music communities.*
