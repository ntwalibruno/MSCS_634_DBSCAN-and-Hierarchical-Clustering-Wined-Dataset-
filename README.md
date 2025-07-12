**Author**: Ntwali Bruno Bahongere  
**Course**: Advanced Big Data and Data Mining  
**Project**: DBSCAN and Hierarchical clustering (Wine Dataset)

## Project Overview

This project implements and compares two unsupervised machine learning clustering algorithms - **DBSCAN** and **Hierarchical Clustering** - on the wine dataset from scikit-learn. The analysis provides insights into the performance, parameter sensitivity, and applicability of each algorithm for wine classification based on chemical properties.

## Dataset

**Wine Dataset from scikit-learn**
- **Size**: 178 samples
- **Features**: 13 chemical properties (alcohol, malic acid, ash, etc.)
- **Classes**: 3 wine varieties (originally labeled)
- **Type**: Real-world chemical analysis data

### Key Features Analyzed
- Alcohol content
- Flavanoids
- Total phenols
- Color intensity
- Malic acid
- Ash content
- And 7 additional chemical properties

## Methodology

### Data Preprocessing
1. **Feature Standardization**: Applied StandardScaler to normalize all features
2. **Dimensionality**: Maintained all 13 original features
3. **Target Separation**: Removed original class labels for unsupervised analysis

### Clustering Algorithms

#### 1. Hierarchical Clustering (Agglomerative)
- **Linkage Method**: Ward linkage (minimizes within-cluster variance)
- **Distance Metric**: Euclidean distance
- **Optimization**: Tested cluster counts using silhouette analysis
- **Visualization**: Complete dendrogram analysis with cut-level exploration

#### 2. DBSCAN (Density-Based Spatial Clustering)
- **Parameter Optimization**: Systematic testing of eps (0.3-1.5) and min_samples (3-6)
- **Method**: k-distance graph for eps selection
- **Noise Handling**: Automatic outlier detection and classification
- **Visualization**: Multi-dimensional scatter plots with noise point analysis

## Key Results

### Performance Comparison

| Metric | Hierarchical Clustering | DBSCAN |
|--------|------------------------|---------|
| **Optimal Clusters** | 3 clusters | Variable (2-4 depending on parameters) |
| **Silhouette Score** | 0.2847 | 0.2439 (best case) |
| **Homogeneity Score** | 0.4019 | 0.2674 |
| **Completeness Score** | 0.4136 | 0.2885 |
| **V-Measure Score** | 0.4077 | 0.2777 |
| **Noise Points** | 0 (all points assigned) | 15-25% (parameter dependent) |

### Key Findings

#### Hierarchical Clustering Advantages
- **Deterministic Results**: Consistent output for same input
- **Complete Hierarchy**: Provides dendrogram for multiple cluster levels
- **Parameter Simplicity**: Only requires number of clusters
- **Better Performance**: Superior scores across all evaluation metrics
- **Wine Variety Separation**: Successfully identifies the 3 wine types

#### DBSCAN Advantages
- **Outlier Detection**: Automatically identifies unusual wine samples
- **Shape Flexibility**: Can handle non-spherical clusters
- **Automatic Clustering**: Determines cluster count automatically
- **Density-Based**: Finds clusters based on local density

#### Parameter Sensitivity Analysis
- **Hierarchical**: Low sensitivity - robust across different cluster counts
- **DBSCAN**: High sensitivity - performance heavily dependent on eps and min_samples tuning

## Technical Implementation

### Dependencies
```python
- scikit-learn (clustering algorithms, metrics)
- pandas (data manipulation)
- numpy (numerical computations)
- matplotlib (visualizations)
- scipy (hierarchical clustering, statistical tests)
```

### Code Structure
1. **Data Loading & Preprocessing** 
2. **Hierarchical Clustering Analysis** 
3. **DBSCAN Implementation** 
4. **Performance Evaluation** 
5. **Comprehensive Comparison** 

## Visualizations

The notebook includes comprehensive visualizations:
- **Dendrograms**: Complete and truncated hierarchical trees
- **Scatter Plots**: Multi-feature cluster visualizations
- **Parameter Analysis**: Silhouette score optimization plots
- **Noise Analysis**: DBSCAN outlier identification
- **Performance Metrics**: Comparative evaluation charts

## Files

- `wine_ds_dbscan_and_hierarchical_clustering.ipynb` - Main analysis notebook
- `README.md` - This documentation file

## Conclusion

The wine dataset analysis reveals that **Hierarchical Clustering** provides better performance for this particular chemical classification task. The globular nature of wine variety clusters and well-separated feature space favor hierarchical approaches over density-based methods. However, DBSCAN's outlier detection capabilities provide valuable insights into unusual wine samples that may represent measurement errors or unique varieties.

---
