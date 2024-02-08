# Netflix Data Analysis

## Table of Contents

- [Project Overview](#project-overview)
- [Data Sources](#data-sources)
- [Tools](#tools)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Data Analysis](#data-analysis)
- [Results](#results)
- [Recommendations](#recommendations)
- [Reference](#reference)

### Project Overview
---

Netflix is one of the most popular media and video streaming platforms. They have over 8000 movies or TV shows on their platform, and as of mid-2021, they have over 200M Subscribers globally. This tabular dataset consists of listings of all the movies and TV shows available on Netflix, along with details such as - cast, directors, ratings, release year, duration, etc. This is an EDA through its data, with a wide range of graphs and visuals.

Add image here

### Data Sources
---

Add data source file and link it here


### Tools
---

- Python (Jupyter Notebook)
- Python Libraries
  - Numpy
  - Pandas
  - Matplotlib

### Exploratory Data Analysis
---

1. What is the month that has the least releases?
2. What are the genres in the data set movies/TV shows?
3. In which year has the largest number of movies/TV shows been released?
4. Which country has released most movies/TV shows?
5. What is the range of duration to movies/TV shows?
6. What is the most popular rating in movies/TV shows?
7. What is the TV show that has the most seasons?

### Data Analysis
---

#### Some Interesting Codes

- In which year has the largest number of movies/TV shows been released?

```python
release_per_year = net.groupby(['release_year'])['type'].value_counts().unstack(level = -1).reset_index()
release_per_year
```

- What are the genres in the data set movies/TV shows?

```python
genres = {}
for genre in movies_df['listed_in']:
  for i in genre.split(','):
    i = i.strip()
    if i not in genres:
      genres[i] = 1
    else:
      genres[i] += 1

movie_genres = pd.DataFrame(list(genres.items()), columns= ['Genre', 'Number of Movies'])
```

### Results
---

From the exploratory data analysis performed on the Netflix dataset, we can conclude that:
- More than 60% of the content on Netflix is movies.
- The best time to add content on Netflix would be between October and December. It is during these months that maximum content is released on Netflix.
- A huge chunk of the content is under the genre of International movies and International TV Shows closely followed by Drama.
- Very few movies and TV shows were released before 2000, post-2000 the numbers started increasing slowly. By 2015 we can see a spike in the number of movies and TV shows released.
- The USA has dominated the space by releasing the maximum number of movies and TV shows. In the top 5 countries producing content on Netflix, India comes a distant second. Closely followed by the UK, Canada, and Japan.
- The popular duration for the movies ranges between 90 - 100 minutes, as the maximum number of movies have been released in this duration range. And TV shows that the public prefers currently seem to be the TV shows with only one season, as the majority of the TV Shows have only one season on Netflix.
- The content produced on Netflix is mostly for mature adults as TV_MA is the most popular rating for movies as well as TV shows released on Netflix.

### Recommendations
---

- A backup plan should be there in tough situations like the pandemic to combat the loss.
- Movie
  - Netflix should be focusing on adding more movies in emerging countries like India, the United Kingdom, Canada, and France for the adult audience.
  - The preferred duration of movies should be from 80-120 minutes.
  - International Movies, Dramas, and Comedies should be the preferred genres for Movies.
- TV Show
  - For TV Shows Netflix should focus on countries like Japan, South Korea, Canada, and France.
  - TV Show seasons can be up to 3 preferably.
  - International TV Shows, TV Dramas, and TV Comedies should be the preferred genres for TV Shows.
 
### Reference
---

- [Kaggle](https://www.kaggle.com/datasets/shivamb/netflix-shows/data)
