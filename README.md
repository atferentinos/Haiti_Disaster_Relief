# Haiti Disaster Relief Image Analysis Project

## Overview
This project develops machine learning models to identify emergency blue tarp shelters from aerial imagery collected after the 2010 Haiti earthquake. The goal is to help disaster relief efforts more efficiently locate and assist displaced persons by automatically detecting temporary shelters from geo-referenced RGB imagery.

## Problem Statement
After natural disasters like the 2010 Haiti earthquake, traditional ground-based relief efforts can be hampered by damaged infrastructure and blocked roads. This project aims to leverage aerial imagery and machine learning to:

* Automatically detect blue emergency shelters (tarps) from RGB pixel data
* Help relief teams better estimate displaced populations
* Enable more efficient resource allocation and aid delivery

## Data
The dataset consists of:
* RGB pixel values (0-255) for aerial imagery
* Binary classification labels:
   * TRUE: Blue tarp present
   * FALSE: No blue tarp present
* Significant class imbalance with only ~3.2% positive cases

## Methodology

### Model Development
Ten different classification models were developed and evaluated:

1. Logistic Regression (LR)
2. Linear Discriminant Analysis (LDA) 
3. Quadratic Discriminant Analysis (QDA)
4. K-Nearest Neighbors (KNN)
5. Penalized Logistic Regression (PLR)
6. Random Forest
7. Boosting
8. Linear SVM
9. Polynomial SVM
10. RBF Kernel SVM

### Model Selection Criteria
* ROC AUC values
* Sensitivity/True Positive Rate (critical for not missing shelters)
* Specificity 
* Precision
* Computational efficiency
* J-index optimization for threshold selection

## Key Findings

### SVM Polynomial Performance
* Perfect ROC AUC (1.0) across training, testing, and cross-validation
* 100% sensitivity for detecting blue tarps
* 98.9% accuracy
* Low false positive rate (0.0111)

### Boosted Model Performance
* 99.4% accuracy
* 100% sensitivity
* Lowest false positive rate (0.00609)

## Practical Considerations

### Computational Efficiency
While SVM Polynomial showed best performance, PLR may be more practical for real-time deployment due to:

* Faster computation time
* Good sensitivity tuning
* Efficient processing of sparse positive cases

### Implementation Challenges
* Need for standardization across relief organizations
* Integration with existing emergency response systems
* Scalability to larger geographic areas
* Image quality variations due to:
   * Time of day
   * Weather conditions
   * Camera specifications

## Future Improvements

### Image Capture
* Standardize timing of aerial photography
* Control lighting conditions
* Use higher quality cameras

### Data Processing
* Filter out irrelevant areas
* Balance class distribution
* Normalize lighting conditions

### System Integration
* Develop standardized output formats
* Create user-friendly interfaces for relief teams
* Enable real-time processing capabilities

## Authors
* Alexandra Ferentinos
* Brendan Jalali
* Pete Landers
