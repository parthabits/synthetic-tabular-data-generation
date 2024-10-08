
# Synthetic Data Generation for Credit Card Fraud Detection

This repository provides an example of generating synthetic data using three different generative models: **CTGAN**, **GaussianCopula**, and **CopulaGAN**. The dataset used is the Kaggle **Credit Card Fraud Detection** dataset, which contains transactions labeled as fraudulent or non-fraudulent.

The primary goal of this code is to generate synthetic data, particularly for the minority class (fraudulent transactions), in order to help balance the dataset and improve the performance of machine learning models in fraud detection tasks.

## Overview

### 1. **Dataset**
The dataset used for synthetic data generation is sourced from the [Kaggle Credit Card Fraud Detection dataset](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud?resource=download). It contains the following features:
- **Class**: The target variable indicating whether a transaction is fraudulent (`1`) or not (`0`).

### 2. **Models Used for Synthetic Data Generation**
The code showcases the use of three different models from the **Synthetic Data Vault (SDV)** library for generating synthetic data:
- **CTGANSynthesizer**: A generative adversarial network (GAN) based model designed for tabular data.
- **GaussianCopulaSynthesizer**: A model based on Gaussian copula for generating data that follows multivariate distributions.
- **CopulaGANSynthesizer**: A GAN-based model that also utilizes copula functions for learning dependencies between features.

### 3. **Key Steps Involved**
- **Data Loading**: The Kaggle Credit Card Fraud dataset is loaded and pre-processed to focus on the minority class (fraudulent transactions).
- **Metadata Definition**: Metadata is automatically detected from the dataset using SDV’s `SingleTableMetadata` to identify column types, distributions, and relationships.
- **Model Training**: The three different models are trained on the fraudulent transaction data.
- **Synthetic Data Generation**: After training, each model generates a synthetic dataset that mimics the original distribution of the fraudulent transactions.

## Workflow

1. **Load the Dataset**: The dataset is loaded and filtered to focus on fraudulent transactions (`Class == 1`).
2. **Define Metadata**: Metadata is generated from the dataframe, which helps the synthesizers understand the structure of the data.
3. **Train the Models**: Each synthesizer (CTGAN, GaussianCopula, CopulaGAN) is trained on the sampled dataset.
4. **Generate Synthetic Data**: After training, each model generates synthetic samples of the minority class.
5. **Compare Results**: The synthetic data generated by each model is compared to the original dataset.

## How to Use

1. **Install Required Packages**:
   To run the code, you'll need to install the following Python packages:
   - `pandas`
   - `sdv`

   You can install them via pip:
   ```bash
   pip install pandas sdv
   ```

2. **Run the Code**: Load the Kaggle dataset and execute the code to generate synthetic data using the three models.

3. **Evaluate the Synthetic Data**: Once generated, the synthetic data can be used for various downstream tasks, such as training machine learning models to detect fraud.

## Models Summary

| Model                     | Description                                                                 |
|----------------------------|-----------------------------------------------------------------------------|
| **CTGANSynthesizer**        | A GAN-based model tailored for generating tabular data.                      |
| **GaussianCopulaSynthesizer**| Generates data by learning a multivariate Gaussian copula.                   |
| **CopulaGANSynthesizer**    | Combines GANs with copula functions for improved learning of dependencies.   |

## Example Outputs

Each synthesizer generates synthetic data that can be compared to the original minority class dataset. The first few rows of the synthetic data are displayed to assess its quality and alignment with the original data distribution.

### Example: CTGAN Synthetic Data
```
Synthetic Dataset:
   <first few rows of synthetic data>
```

### Example: GaussianCopula Synthetic Data
```
Synthetic Dataset using GaussianCopula:
   <first few rows of synthetic data>
```

### Example: CopulaGAN Synthetic Data
```
Synthetic Dataset using CopulaGAN:
   <first few rows of synthetic data>
```

## Conclusion

This repository demonstrates how synthetic data generation techniques can be applied to imbalanced datasets to generate realistic samples of the minority class. By using these methods, you can improve your model’s performance in detecting fraudulent transactions by providing it with more data to learn from.

## Resources

- [SDV Documentation](https://sdv.dev/SDV/)
- [Kaggle Credit Card Fraud Detection Dataset](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud?resource=download)

Feel free to experiment with these models and adapt them to your own datasets and use cases!
