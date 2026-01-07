# Multimodal Property Price Prediction

Predicting house prices by combining tabular housing data with satellite imagery using CNNs and XGBoost.

## Project Summary

This project explores whether satellite imagery provides complementary information to traditional tabular housing features for property price prediction.

## Dataset description

The tabular dataset contains house attributes such as (sqft,bedrooms,grade,condition,sqft15 etc...) and lat,long of the house.
We fetch the images through sentinelhub api using coordinates 

## Pipeline

- XGBoost for tabular predictions 
- Pretrained RESNET-50 for image embeddings 
- PCA for reducing dimesnions ofnour embeddings 
- Stacking-based late fusion for final prediction

## Result 
| Model| R² |
|------|----|
| Tabular XGBoost | ~0.9007 |
| Image-only NN | ~0.17 |
| Stacking Fusion | ~0.9018 |
<br>
| Model| RMSE |
|------|----|
| Tabular XGBoost | ~0.1654 |
| Image-only NN | ~0.4788 |
| Stacking Fusion | ~0.1646 |

## Explainability
-Grad-CAM used to visualize image regions influencing predictions

## Repository Structure
- notebooks/ : Jupyter notebooks
- data/ : CSV datasets
- report/ : Final PDF report
- submission.csv

## How to Run
1. Install dependecies 'pip install -r requirements.txt
2. Add api key from sentinel hub to api.txt
3. Run notebooks in order from `notebooks/`

##  Notes
Satellite images and API keys are excluded from the repository.