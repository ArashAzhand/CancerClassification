
# Classifying Cancer Types Using Gene Expressions

This project focuses on classifying different cancer types using high-dimensional gene expression data. By understanding gene activity patterns, we can support early diagnosis and enable more personalized treatment approaches — a crucial step in modern precision medicine.  

## Motivation

Cancer is fundamentally a genetic disease. Gene expressions — the level at which certain genes are turned on or off — can provide critical clues about cancer types. However, working with gene expression data is challenging because of its **high dimensionality** (tens of thousands of genes) and **low sample size**, which makes traditional analysis and modeling very difficult.

## 🧬 Dataset

We used a subset of the **CuMiDa (Curated Microarray Database)**, which contains 54,675 gene expression features across 151 samples. The samples are labeled into 6 classes:

1. Basal
2. HER2
3. Luminal_B
4. Luminal_A
5. Cell_line
6. Normal

 **Dataset link**: [CuMiDa dataset](https://www.kaggle.com/datasets/brunogrisci/breast-cancer-gene-expression-cumida)  

> Each sample represents one instance with thousands of gene expression values, making it a classic example of a **high-dimensional, low-sample, multi-class classification problem**.

## Data Exploration

We started with:

- **Class distribution analysis** to understand potential imbalances.
- **Gene expression variability** checks to identify noise and uninformative genes.

## Preprocessing & Feature Selection

To reduce dimensionality and improve learning efficiency, we performed:

- **Variance thresholding**: Removed genes with low variance across samples.
- **ANOVA F-test**: Selected the top 1,000 genes most informative for distinguishing cancer types.

This drastically reduced noise and improved model stability.

## Machine Learning Models

We evaluated multiple models using **stratified 5-fold cross-validation**:

- Logistic Regression
- SVM with RBF kernel
- Random Forest

**Key finding**: Random Forest achieved the best performance overall, while Logistic Regression was most sensitive to irrelevant features.

## Visualization

We used **PCA (Principal Component Analysis)** to project the data into 2D space. The results showed that different cancer types became nearly linearly separable after feature selection, highlighting the power of proper preprocessing.

![image](https://github.com/user-attachments/assets/6b595dc0-2e49-4a0b-9631-af2d2c7d358b)


## Results

- Feature selection significantly boosted model performance compared to using the raw dataset.
- PCA plots demonstrated clear separability between classes.
- Despite the dataset complexity, careful preprocessing enabled surprisingly high accuracy.

## Conclusion

- Importance of feature selection in high-dimensional data.
- Random Forest was the most robust model for this task.
- Visualization confirmed that our selected genes carry meaningful information about cancer types.

## Resources

- [CuMiDa: An Extensively Curated Microarray Database for Benchmarking and Testing of Machine Learning Approaches in Cancer Research](https://www.liebertpub.com/doi/10.1089/cmb.2018.0238)
- [Neuroevolution as a Tool for Microarray Gene Expression Pattern Identification in Cancer Research](https://www.sciencedirect.com/science/article/pii/S1532046418302260?via%3Dihub)


*Let's harness AI and data science to make a real impact in healthcare!*
