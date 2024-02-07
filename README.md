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


