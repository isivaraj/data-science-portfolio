# Projects
This section documents my data science projects, research questions, and data stories I create throughout the semesters.
---
## Project 1

### Research Question

Do movies with higher budgets tend to receive higher audience ratings and earn more revenue?

### Background

Movie studios spend very different amounts of money producing films. Larger budgets can allow studios to hire well-known actors, use more advanced special effects, increase marketing, and expand distribution.

I chose this topic because I wanted to see whether spending more money on a movie is actually connected to better outcomes. A larger budget may help a movie earn more money, but it does not necessarily mean audiences will enjoy the movie more.

This question could be useful for movie studios, producers, and even movie fans because it helps show whether production spending is more strongly connected to financial success or audience reception.

This project compares movie budget with both audience ratings and revenue to see which relationship is stronger.

### Dataset Source

The data for this project comes from The Movie Database (TMDB) API.

I chose TMDB because it provides movie information including budget, revenue, audience ratings, genre, and release date in one source, which makes it useful for comparing financial information with audience reactions.

The dataset originally included 100 movies.

### Unit of Analysis

Each row in the dataset represents one movie.

### Features and Variables

The dataset includes the following variables:

- **Movie Title:** Identifies each movie.
- **Budget:** The amount of money spent to produce the movie.
- **Revenue:** The amount of money the movie earned.
- **Audience Rating:** The average TMDB user rating for the movie.
- **Release Date:** The date the movie was released.

### Dataset Size
The original dataset contained 100 movies. After removing movies with missing or unusable budget and revenue values, 62 movies remained for analysis.

### Missing Values
Some movies had a budget or revenue value of 0, which was treated as missing or unusable data. These movies were removed because they could not be used to analyze the relationship between budget, revenue, and audience rating.

### Data Cleaning
The data was cleaned using pandas. Movies with a budget of 0 or revenue of 0 were treated as having missing or unusable financial data and were removed.

The original dataset had 100 movies, and 62 movies remained after cleaning.

### Visualizations
 ![Budget vs Audience Rating](budget_vs_rating.png)
 
 ![Budget vs Revenue](budget_vs_revenue.png)
 
#### Budget vs Audience Rating

The first visualization compares movie budget with audience rating.

There is a slight upward trend, but the points are widely spread out. This suggests that spending more money on a movie does not guarantee that audiences will rate it much higher.

This is interesting because it shows that factors other than budget, such as story, acting, genre, or audience expectations, may play an important role in how viewers rate a movie.

#### Budget vs Revenue

The second visualization compares movie budget with revenue.

This graph shows a much clearer positive relationship. Movies with larger budgets generally tended to earn more revenue.

Compared with the audience-rating graph, the pattern is much stronger. This suggests that production spending may have a stronger relationship with financial performance than with audience satisfaction.

### Results

The results showed two very different relationships.

The correlation between movie budget and audience rating was about **0.38**, which represents a weak-to-moderate positive relationship. Higher-budget movies sometimes received higher audience ratings, but the relationship was not very strong.

The correlation between movie budget and revenue was about **0.76**, which represents a strong positive relationship. Movies with larger production budgets generally tended to earn more revenue.

The most interesting result was the difference between these two correlations. Budget was much more strongly related to revenue than it was to audience rating.

This suggests that spending more money may help a movie achieve greater financial success through factors such as production scale, marketing, or distribution, but spending more money does not necessarily make audiences enjoy the movie more.

Overall, the results suggest that budget appears to be more useful for explaining financial performance than audience satisfaction.

### Interesting Findings

One of the most interesting findings was that the two outcomes behaved differently even though they were compared with the same variable.

Budget had only a moderate relationship with audience ratings but had a strong relationship with revenue.

This shows why it is important to examine more than one measure of movie success. A movie can be financially successful without receiving especially high audience ratings, while a highly rated movie does not necessarily need one of the largest production budgets.

The visualizations also show that not every movie follows the overall trend. Some movies appear farther away from the main pattern, showing that budget alone cannot explain every movie's performance.

### Limitations

This analysis has several limitations.

The original dataset contained 100 movies, but movies with a budget or revenue value of 0 were removed because those values could not be used reliably. This reduced the final dataset to 62 movies.

Removing these movies may have affected the results because films with missing financial information may differ from the movies that remained in the dataset.

The dataset also contains a sample of popular movies from TMDB, so it may not represent all movies equally. Smaller independent films, older movies, or less popular movies may be underrepresented.

Audience ratings also have limitations because they depend on who chooses to rate a movie and how many users submit ratings.

Finally, correlation does not prove causation. The results show that budget and revenue are strongly related in this sample, but they do not prove that increasing a movie's budget will automatically increase its revenue. Other factors such as marketing, franchise popularity, release timing, genre, and star power could influence the results.

### Conclusion

This project asked whether movies with higher budgets tend to receive higher audience ratings and earn more revenue.

The results suggest that the answer depends on how movie success is measured.

Higher budgets had only a weak-to-moderate relationship with audience ratings, while they had a much stronger relationship with revenue.

This means that a larger production budget may be associated with greater financial success, but it does not guarantee that audiences will rate a movie more highly.

The project helped show that financial success and audience satisfaction are different outcomes and that looking at both provides a more complete picture of movie performance.

### Code
[View Project Notebook](https://github.com/isivaraj/data-science-portfolio/blob/main/movie_project.ipynb)

### References

Simonton, D. K. (2005). Cinematic creativity and production budgets: Does money make the movie? *The Journal of Creative Behavior, 39*(1), 1–15. https://doi.org/10.1002/j.2162-6057.2005.tb01246.x

Ravid, S. A. (1999). Information, blockbusters, and stars: A study of the film industry. *The Journal of Business, 72*(4), 463–492. https://doi.org/10.1086/209624

Moon, S., Bergey, P. K., & Iacobucci, D. (2010). Dynamic effects among movie ratings, movie revenues, and viewer satisfaction. *Journal of Marketing, 74*(1), 108–121. https://doi.org/10.1509/jmkg.74.1.108

### AI Usage
AI tools were used to help organize the project, explain concepts, and improve the clarity of the written sections. The data analysis, code, and final interpretations were reviewed and completed by me.

---

## Project 2: Predicting Calories from Nutritional Information

### Research Question

Can the nutritional characteristics of a food be used to predict its calorie content?

### Background

Calories represent the amount of energy provided by food. Nutritional factors such as protein, carbohydrates, fat, fiber, and sodium may help explain differences in calorie content.

This project uses machine learning to predict calories based on nutritional information.

### Dataset Source

The data comes from the USDA FoodData Central Foundation Foods dataset.

### Unit of Analysis

Each row in the final dataset represents one food.

### Target Variable

The target variable is:

- Calories

This is a regression problem because calories are numerical values.

### Features and Variables

The predictor variables used in the model are:

- Protein
- Carbohydrates
- Fat
- Fiber
- Sodium

### Dataset Size

Before removing missing values, the merged Foundation Foods dataset contained 448 foods.

After removing rows with missing values, 54 foods remained for modeling.

### Missing Values

Some foods were missing one or more of the nutritional variables needed for modeling.

Rows with missing values were removed so that every observation contained complete information for the selected features and target.

### Data Cleaning

The food and nutrient datasets were combined using the USDA FoodData Central ID.

Only Foundation Foods were included.

The data was organized so that each food had values for calories, protein, carbohydrates, fat, fiber, and sodium.

Rows with missing values were removed.

### Visualizations

#### Distribution of Calories

![Distribution of Calories](calorie_distribution.png)

The calorie distribution shows that foods in the dataset have a wide range of calorie values.

Some foods have much higher calorie values than others, which may affect model performance.

#### Fat vs Calories

Foods with higher fat values generally tended to have higher calorie values.

This helped support including fat as one of the predictor variables.

### Train/Test Split

The dataset was divided into:

- 80% training data
- 20% testing data

A fixed `random_state=42` was used so the split could be reproduced.

The models were trained only on the training data and evaluated using the testing data.

### Baseline Model

A baseline model was created before training the machine-learning models.

The baseline predicted the average calorie value from the training set for every food in the test set.

This provided a benchmark for comparing the machine-learning models.

### Machine Learning Models

Two regression models were trained:

#### Linear Regression

Linear Regression was used because calories are numerical and nutritional features have measurable relationships with calorie content.

#### K-Nearest Neighbors Regression

KNN Regression predicts calories using foods with similar nutritional characteristics.

The predictor variables were standardized before using KNN because the model relies on distances between observations.

### Results

Mean Absolute Error (MAE) was used to compare model performance.

MAE measures the average difference between the predicted calorie values and the actual calorie values.

A lower MAE represents better model performance.

| Model | MAE |
|---|---:|
| Baseline | ADD BASELINE MAE |
| Linear Regression | ADD LINEAR MAE |
| KNN Regression | ADD KNN MAE |

![Model MAE Comparison](model_mae_comparison.png)

The best-performing model was:

**ADD FINAL MODEL HERE**

This model was selected because it had the lowest Mean Absolute Error.

### Model Interpretation

The results suggest that nutritional features contain useful information for predicting calorie content.

Fat, carbohydrates, and protein are especially relevant because they contribute to the energy content of food.

The model may perform less accurately for foods with unusual nutritional values or extreme calorie amounts.

### Limitations

This project has several limitations.

Only 54 foods remained after removing missing values, so the final dataset is relatively small.

The dataset may not represent all food categories equally.

Removing rows with missing values may also affect the types of foods included in the final analysis.

Because of these limitations, the results should not be used as a replacement for official nutrition labels or professional dietary advice.

### Future Improvements

Future work could include:

- Using a larger dataset
- Including additional nutritional features
- Testing more regression models
- Using cross-validation
- Performing hyperparameter tuning

### Code

[View Project Notebook](nutrition_project.ipynb)

[View Cleaned Dataset](food_nutrition_clean.csv)

### References

National Academies of Sciences, Engineering, and Medicine. (2023). *Dietary reference intakes for energy*. National Academies Press.

National Institute of Environmental Health Sciences. (n.d.). *Nutrition, health, and your environment*. National Institutes of Health.

U.S. Department of Agriculture. (n.d.). *FoodData Central*. U.S. Department of Agriculture.

U.S. Department of Agriculture & U.S. Department of Health and Human Services. (2020). *Dietary Guidelines for Americans, 2020–2025* (9th ed.).

### AI Usage

AI tools were used to help organize the project, explain concepts, and improve the clarity of the written sections. The data analysis, code, and final interpretations were reviewed and completed by me.
