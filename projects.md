# Projects
This section documents my data science projects, research questions, and data stories I create throughout the semesters.
---
## Project 1

### Research Question

Do movies with higher budgets tend to receive higher audience ratings and earn more revenue?

### Dataset Source

The data for this project will come from The Movie Database (TMDB) API. The dataset will include movie information such as budget, revenue, audience rating, genre, and release date.

That covers the source part of the rubric, but later we’ll still need to add the dataset’s unit of analysis,

### Unit of Analysis

Each row in the dataset represents one movie.

### Features and Variables

The dataset will include the following variables:

- Movie Title
- Budget
- Revenue
- Audience Rating
- Genre
- Release Year

### Variable Descriptions

- **Budget:** The amount of money spent to produce the movie.
- **Revenue:** The amount of money the movie earned.
- **Audience Rating:** The average rating given by viewers.
- **Genre:** The category or type of movie.
- **Release Year:** The year the movie was released.

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

The first visualization compares movie budget and audience rating. The graph shows that higher-budget movies do not always receive much higher ratings.

#### Budget vs Revenue

The second visualization compares movie budget and revenue. The graph shows a clearer positive relationship, where higher-budget movies tend to earn more revenue.

### Results

The correlation between movie budget and audience rating was about 0.38, which shows a weak-to-moderate positive relationship. This means that higher-budget movies sometimes receive higher ratings, but the relationship is not very strong.

The correlation between movie budget and revenue was about 0.76, which shows a strong positive relationship. This suggests that movies with higher budgets tend to earn more revenue.

### Limitations
This analysis has several limitations. Some movies were removed because TMDB listed their budget or revenue as 0, which reduced the dataset from 100 movies to 62 movies.

The dataset also only includes a sample of popular movies from TMDB, so it may not represent all movies equally. Audience ratings can also be influenced by who chooses to rate a movie and how many people rated it.

Because of these limitations, the results show relationships in this sample but do not prove that a higher budget directly causes higher ratings or revenue.

### Code
[View Project Notebook](movie_project.ipynb)

### References
At least three peer-reviewed sources related to movie budgets, audience ratings, revenue, or film performance will be included here in APA format.

### AI Usage
AI tools were used to help organize the project, explain concepts, and improve the clarity of the written sections. The data analysis, code, and final interpretations were reviewed and completed by me.
