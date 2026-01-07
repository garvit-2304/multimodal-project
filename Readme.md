# Multimodal Property Price Prediction

Predicting house prices by combining tabular housing data with satellite imagery using CNNs and XGBoost.

## Project Summary

This project explores whether satellite imagery provides complementary information to traditional tabular housing features for property price prediction. We used a deep learning frameworks that combines(CNNs) for visual feature extraction from sentinel hub and XGBoost for tabular predictions. The fusion architecture leverages spatial environmental features: including vegetation density, urban infrastructure patterns, and geographic context alongside conventional property attributes such as square footage, location, and amenities 


## Dataset description

The tabular dataset contains house attributes such as (sqft,bedrooms,grade,condition,sqft15 etc...) and lat,long of the house.
We fetch the images through sentinelhub api using coordinates . For generating images we normalised it and used cloud filtering and aligned synchroniously our property coordinates

## Pipeline

- XGBoost for tabular predictions 
- Pretrained RESNET-50 for image embeddings 
- PCA for reducing dimesnions of our embeddings 
- Stacking-based late fusion for final prediction

## Result 
| Model| R² | RMSE |
|------|----|------|
| Tabular XGBoost | ~0.9007 | ~0.1654 |
| Image-only NN | ~0.17 | ~0.4788 |
| Stacking Fusion | ~0.9018 | ~0.1646 |


## Explainability
-Grad-CAM used to visualize image regions influencing predictions

## Repository Structure
- notebooks/: Jupyter notebooks
- data/: CSV datasets
- report/: Final PDF report
- submission.csv

## How to Run
1. Install dependecies 'pip install -r requirements.txt
2. Create a text file api.txt and generate client-id and client secret from sentinel hub
3. Add these two to api.txt
4. Run notebooks in order from `notebooks/`

##  Notes
Satellite images and API keys are excluded from the repository.
