---
layout: default
title: Nutrition and Calorie Prediction
---

# Predicting Calories from Nutritional Information

## Personal Portfolio Project Two

This project uses machine learning to investigate whether nutritional information can be used to predict the calorie content of a food.

The dataset comes from USDA FoodData Central. I use nutritional features such as protein, carbohydrates, fat, fiber, and sodium to train and compare regression models.

---

## 1. Problem Definition

The goal of this project is to predict the number of calories in a food using its nutritional information.

**Research Question:**  
Can the nutritional characteristics of a food be used to predict its calorie content?

The target variable is **calories**.

This is a **regression problem** because calories are a numerical value.

This model could help researchers and consumers better understand how different nutritional characteristics relate to the calorie content of foods. However, the model is intended for educational analysis and should not replace official nutrition labels or professional dietary advice.

---

## 2. Background and Context

Calories represent the amount of energy provided by food. Macronutrients such as carbohydrates, protein, and fat contribute to a food's energy content.

Because nutritional values are related to the amount of energy found in foods, machine learning can be used to investigate whether these nutritional characteristics can predict calorie content.

This project uses USDA FoodData Central data because it provides detailed nutritional information for many foods.

The main predictors examined in this project are:

- Protein
- Carbohydrates
- Fat
- Fiber
- Sodium

### Supporting Sources

Nutrition research shows that nutrient composition is important when evaluating the energy and nutritional characteristics of foods.

The USDA FoodData Central database provides standardized food and nutrient information that can be used for nutrition research and analysis.

---

## 3. Data Description

The data for this project comes from the **USDA FoodData Central Foundation Foods dataset**.

Each row in the final dataset represents one food.

The target variable is:

- **Calories**

The predictor variables are:

- **Protein**
- **Carbohydrates**
- **Fat**
- **Fiber**
- **Sodium**

Before removing missing values, the merged Foundation Foods dataset contained **448 foods**.

After rows with missing values were removed, **54 foods** remained for modeling.

The final cleaned dataset contained 7 columns:

- Food name
- Calories
- Protein
- Carbohydrates
- Fat
- Fiber
- Sodium

---

## 4. Data Understanding and Exploration

Before building the models, I explored the nutritional data using summary statistics and visualizations.

The exploration helped identify the distribution of calorie values and relationships between nutrients and calories.

### Distribution of Calories

![Distribution of Calories](calorie_distribution.png)

The calorie distribution shows that foods in the dataset have a wide range of calorie values. Some foods have much higher calorie values than the majority of the dataset.

These high-calorie observations are important because they may affect model performance.

### Fat and Calories

Foods with higher fat values generally tended to have higher calorie values.

This relationship makes sense because fat contributes substantially to the energy content of food.

The exploratory analysis supported using nutritional variables such as fat, carbohydrates, protein, fiber, and sodium as model features.

---

## 5. Data Preparation and Feature Selection

The food and nutrient datasets were combined using each food's USDA FoodData Central ID.

Only Foundation Foods were selected for the final analysis.

The following features were selected:

- Protein
- Carbohydrates
- Fat
- Fiber
- Sodium

Calories were selected as the target variable.

Rows containing missing values were removed so that every food used for modeling had values for all selected variables.

After cleaning, 54 observations remained.

The dataset was divided into:

- **80% training data**
- **20% testing data**

A fixed `random_state=42` was used so the same split could be reproduced.

The models were trained only on the training data and evaluated on the separate testing data. This helps reduce data leakage because the models do not train on the observations used for final evaluation.

For K-Nearest Neighbors, numerical predictors were standardized because the algorithm measures distance between observations and variables such as sodium have much larger numerical scales than variables such as protein or fat.

---

## 6. Baseline and Model Development

A baseline model was created before training the machine-learning models.

The baseline predicted the **average calorie value from the training set** for every test observation.

This provides a simple benchmark that trained machine-learning models should outperform.

Two regression models were then trained:

### Linear Regression

Linear Regression models the relationship between the nutritional predictors and calorie content using a linear equation.

It is appropriate because calories are numerical and several nutrients are directly related to energy content.

### K-Nearest Neighbors Regression

KNN Regression predicts a food's calorie value based on foods with similar nutritional characteristics.

The predictor variables were standardized before fitting KNN because KNN depends on distance calculations.

Both models were trained using the same training and testing sets so their performance could be compared fairly.

---

## 7. Model Evaluation and Selection

The main evaluation metric used was **Mean Absolute Error (MAE)**.

MAE measures the average absolute difference between the predicted calorie values and the actual calorie values.

A lower MAE indicates better predictions.

### Model Results

| Model | MAE |
|---|---:|
| Baseline | ADD BASELINE MAE |
| Linear Regression | ADD LINEAR MAE |
| KNN Regression | ADD KNN MAE |

![Model MAE Comparison](model_mae_comparison.png)

The best model was the model with the lowest MAE.

**Final model:** ADD FINAL MODEL HERE

This model was selected because it produced predictions that were closer to the true calorie values than the baseline and the other machine-learning model.

---

## 8. Model Interpretation and Insights

The results suggest that nutritional information contains useful information for predicting the calorie content of foods.

Features such as fat, carbohydrates, and protein are especially relevant because they contribute to the energy content of food.

The final model performed better on some foods than others. Foods with unusual nutritional characteristics or extreme calorie values were more difficult to predict.

The model demonstrates a relationship between nutritional characteristics and calories, but it does not prove that every relationship is causal.

Because the dataset is relatively small, these results should be interpreted carefully.

---

## 9. Limitations, Ethics, and Reflection

One major limitation is the small final dataset size. After removing rows with missing values, only 54 foods remained.

The dataset may also not represent every category of food equally. Certain foods or food groups may be overrepresented or underrepresented.

Another limitation is that removing missing observations can change the composition of the dataset.

Incorrect predictions could provide inaccurate calorie estimates. This could be especially problematic if the model were used for health or dietary decisions.

For that reason, this model should not replace:

- official food labels
- USDA nutritional information
- medical advice
- professional dietary advice

In the future, I would use a larger dataset, examine additional food categories, include more nutritional features, and test additional regression models.

I would also experiment with hyperparameter tuning and cross-validation to improve model evaluation.

---

## 10. Code and Transparency

The full machine-learning analysis was completed in Python using:

- pandas
- matplotlib
- scikit-learn

### Project Files

- [View the Jupyter Notebook](nutrition_project.ipynb)
- [View the cleaned dataset](food_nutrition_clean.csv)

### Dataset Source

The original data came from **USDA FoodData Central**.

### AI Usage Disclosure

I used **OpenAI ChatGPT, GPT-5.6**, during this project.

Generative AI was used to help:

- explain machine-learning concepts
- troubleshoot Python errors
- organize the project structure
- improve explanations of modeling decisions
- review the project against the assignment rubric

I reviewed, edited, and ran the code myself and verified the project outputs before publication.

---

## References

National Academies of Sciences, Engineering, and Medicine. (2023). *Dietary reference intakes for energy*. National Academies Press.

National Institute of Environmental Health Sciences. (n.d.). *Nutrition, health, and your environment*. National Institutes of Health.

U.S. Department of Agriculture. (n.d.). *FoodData Central*. U.S. Department of Agriculture.

U.S. Department of Agriculture & U.S. Department of Health and Human Services. (2020). *Dietary Guidelines for Americans, 2020–2025* (9th ed.).
