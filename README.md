# 🧬 WildLifespan: Animal Lifespan Prediction

A regression project and Streamlit web app that estimates an animal's lifespan from its **top speed (km/h)** and **body mass (kg)**.

The question behind it: *can two simple physical traits predict how long an animal lives?* The notebook compares a linear and a polynomial model and reports honestly how well each one does.

## What's inside

| File | Purpose |
|---|---|
| `WildLifespan_Animal_Lifespan_Prediction.ipynb` | Full walkthrough: load data, clean, explore, train, evaluate, save models |
| `App.py` | Streamlit app that loads the saved models and predicts from user input |
| `animal_species_200_rows.csv` | Dataset of 200 animal records (type, name, speed, weight, lifespan and more) |
| `linear_model.pkl`, `poly_model.pkl`, `poly_converter.pkl` | Trained Linear Regression, Polynomial Regression (degree 2) and the feature transformer |

## The pipeline

1. Load and clean the data (keep Speed, Weight, Lifespan)
2. Explore it with a correlation heatmap and a lifespan distribution
3. Split 80% train / 20% test
4. Train **Linear Regression** and **Polynomial Regression (degree 2)**
5. Compare them with the R² score and an actual-vs-predicted plot
6. Save the models with `pickle` for the app

## Findings

Both models score a **low R²**. In this dataset, speed and weight are weak predictors of lifespan: many heavy animals live short lives and many light ones live long ones. Factors like diet, habitat, predators and reproduction matter much more. The project is best read as a clear example of the full ML workflow, and of recognising when features are not informative enough. It is not a reliable lifespan calculator.

## Run the app

Requires Python 3.9+.

```bash
git clone https://github.com/Hammad-Ahmed-hk/Wild_Life_Span.git
cd Wild_Life_Span
pip install -r requirements.txt
streamlit run App.py
```

In the app, choose a model (Linear Regression or Polynomial), enter speed and body mass, and read the predicted lifespan.

> The `.pkl` files were saved with scikit-learn. If loading fails after a major version change, re-run the notebook to regenerate them.

## Tech stack

Python, pandas, NumPy, scikit-learn, Matplotlib, Seaborn, Streamlit

## Author

Hammad Ahmed, [@Hammad-Ahmed-hk](https://github.com/Hammad-Ahmed-hk)
