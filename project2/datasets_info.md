## TMDb Movies Dataset

https://www.kaggle.com/datasets/juzershakir/tmdb-movies-dataset

Contains information about 10k+ movies collected from TMDb.

**tmdb_movies_data.csv (6.85 MB)**
- id (int) - TMDb ID
- imdb_id (string) - IMDb ID
- popularity (float) - Popularity score
- budget (int) - Budget allocated
- revenue (int) - Total revenue generated
- original_title (string)
- cast (string) - Pipe-delimited
- homepage (string) - Official homepage URL
- director (string)
- tagline (string) - Catchphrase
- keywords (string) - Pipe-delimited
- overview (string) - Brief description or summary
- runtime (int) - Duration in minutes
- genres (string) - Pipe-delimited
- production_companies (string) - Pipe-delimited
- release_date (string) - Format 6/9/2015
- vote_count (int) - Total count of votes received
- vote_average (float) - Average vote or rating given by viewers
- release_year (int)
- budget_adj (float) - Budget adjusted to 2010 values
- revenue_adj (float) - Revenue adjusted to 2010 values

## Full TMDB Movies Dataset 2024 (1M Movies)

https://www.kaggle.com/datasets/asaniczka/tmdb-movies-dataset-2023-930k-movies

The TMDb (The Movie Database) is a comprehensive movie database that provides information about movies, including details like titles, ratings, release dates, revenue, genres, and much more.

This dataset contains a collection of 1,000,000 movies from the TMDB database.

**TMDB_movie_dataset_v11.csv (594.34 MB)**
- id (int) - TMDb ID
- title (string)
- vote_average (float) - Average vote or rating given by viewers
- vote_count (int) - Total count of votes received
- status (string) - e.g., Released, Rumored, Post Production
- release_date (string) - Format 2010-07-15
- revenue (int) - Total revenue generated
- runtime (int) - Duration in minutes
- adult (bool) - Indicates if movie is suitable only for adult audiences
- backdrop_path (string) - Relative URL of backdrop image
- budget (int) - Budget allocated
- homepage (string) - Official homepage URL
- imdb_id (string) - IMDb ID
- original_language (string) - Original language in which the movie was produced
- original_title (string)
- overview (string) - Brief description or summary
- popularity (float) - Popularity score
- poster_path (string) - Relative URL of poster image
- tagline (string) - Catchphrase
- genres (string) - CSV
- production_companies (string) - CSV of production companies involved
- production_countries (string) - CSV of countries involved in production
- spoken_languages (string) - CSV of languages spoken in the movie
- keywords (string) - CSV

## IMDb Non-Commercial Datasets

https://developer.imdb.com/non-commercial-datasets/
https://datasets.imdbws.com/

Each dataset is contained in a gzipped, tab-separated-values (TSV) formatted file in the UTF-8 character set. The first line in each file contains headers that describe what is in each column. A '\N' is used to denote that a particular field is missing or null for that title/name. The available datasets are as follows:

**title.akas.tsv.gz**
- titleId (string) - a tconst, an alphanumeric unique identifier of the title
- ordering (integer) – a number to uniquely identify rows for a given titleId
- title (string) – the localized title
- region (string) - the region for this version of the title
- language (string) - the language of the title
- types (array) - Enumerated set of attributes for this alternative title. One or more of the following: "alternative", "dvd", "festival", "tv", "video", "working", "original", "imdbDisplay". New values may be added in the future without warning
- attributes (array) - Additional terms to describe this alternative title, not enumerated
- isOriginalTitle (boolean) – 0: not original title; 1: original title

**title.basics.tsv.gz**
- tconst (string) - alphanumeric unique identifier of the title
- titleType (string) – the type/format of the title (e.g. movie, short, tvseries, tvepisode, video, etc)
- primaryTitle (string) – the more popular title / the title used by the filmmakers on promotional materials at the point of release
- originalTitle (string) - original title, in the original language
- isAdult (boolean) - 0: non-adult title; 1: adult title
- startYear (YYYY) – represents the release year of a title. In the case of TV Series, it is the series start year
- endYear (YYYY) – TV Series end year. '\N' for all other title types
- runtimeMinutes – primary runtime of the title, in minutes
- genres (string array) – includes up to three genres associated with the title

**title.crew.tsv.gz**
- tconst (string) - alphanumeric unique identifier of the title
- directors (array of nconsts) - director(s) of the given title
- writers (array of nconsts) – writer(s) of the given title

**title.episode.tsv.gz**
- tconst (string) - alphanumeric identifier of episode
- parentTconst (string) - alphanumeric identifier of the parent TV Series
- seasonNumber (integer) – season number the episode belongs to
- episodeNumber (integer) – episode number of the tconst in the TV series

**title.principals.tsv.gz**
- tconst (string) - alphanumeric unique identifier of the title
- ordering (integer) – a number to uniquely identify rows for a given titleId
- nconst (string) - alphanumeric unique identifier of the name/person
- category (string) - the category of job that person was in
- job (string) - the specific job title if applicable, else '\N'
- characters (string) - the name of the character played if applicable, else '\N'

**title.ratings.tsv.gz**
- tconst (string) - alphanumeric unique identifier of the title
- averageRating – weighted average of all the individual user ratings
- numVotes - number of votes the title has received

**name.basics.tsv.gz**
- nconst (string) - alphanumeric unique identifier of the name/person
- primaryName (string)– name by which the person is most often credited
- birthYear – in YYYY format
- deathYear – in YYYY format if applicable, else '\N'
- primaryProfession (array of strings)– the top-3 professions of the person
- knownForTitles (array of tconsts) – titles the person is known for

## Netflix Movies and TV Shows

https://www.kaggle.com/datasets/shivamb/netflix-shows

Netflix is one of the most popular media and video streaming platforms. They have over 8000 movies or tv shows available on their platform. This tabular dataset consists of listings of all the movies and tv shows available on Netflix, along with details such as - cast, directors, ratings, release year, duration, etc.

**netflix_titles.csv (3.4 MB)**
- show_id (string) - Unique ID
- type (string) - Identifier (Movie or TV Show)
- title (string)
- director (string)
- cast (string) - CSV
- country (string) - Country where it was produced
- date_added (string) - Date added on Netflix (e.g. September 25, 2021)
- release_year (int)
- rating (string) - TV Rating (e.g. PG-13)
- duration (string) - Duration in minutes or seasons (e.g. 90 min, 2 Seasons)
- listed_in (string) - Genre CSV
- description (string) - Summary description

## Hulu Movies and TV Shows

https://www.kaggle.com/datasets/shivamb/hulu-movies-and-tv-shows

Hulu is exclusive to the United States and is not available in other countries. This tabular dataset consists of listings of all the movies and tv shows available on Hulu, along with details such as - cast, directors, ratings, release year, duration, etc.

**hulu_titles.csv (1.11 MB)**
- show_id (string) - Unique ID
- type (string) - Identifier (Movie or TV Show)
- title (string)
- director (string)
- cast (string) - CSV
- country (string) - Country where it was produced
- date_added (string) - Date added on Netflix (e.g. September 25, 2021)
- release_year (int)
- rating (string) - TV Rating (e.g. PG-13)
- duration (string) - Duration in minutes or seasons (e.g. 90 min, 2 Seasons)
- listed_in (string) - Genre CSV
- description (string) - Summary description

## Disney+ Movies and TV Shows

https://www.kaggle.com/datasets/shivamb/disney-movies-and-tv-shows

Disney+ has close to 1300 movies or tv shows available on their platform as of mid-2021. This tabular dataset consists of listings of all the movies and tv shows available on Disney+, along with details such as - cast, directors, ratings, release year, duration, etc.

**disney_plus_titles.csv (383.57 kB)**
- show_id (string) - Unique ID
- type (string) - Identifier (Movie or TV Show)
- title (string)
- director (string)
- cast (string) - CSV
- country (string) - Country where it was produced
- date_added (string) - Date added on Netflix (e.g. September 25, 2021)
- release_year (int)
- rating (string) - TV Rating (e.g. PG-13)
- duration (string) - Duration in minutes or seasons (e.g. 90 min, 2 Seasons)
- listed_in (string) - Genre CSV
- description (string) - Summary description

## Amazon Prime Movies and TV Shows

https://www.kaggle.com/datasets/shivamb/amazon-prime-movies-and-tv-shows

Amazon Prime has close to 10000 movies or tv shows available on their platform as of mid-2021. This tabular dataset consists of listings of all the movies and tv shows available on Amazon Prime, along with details such as - cast, directors, ratings, release year, duration, etc.

**amazon_prime_titles.csv (3.97 MB)**
- show_id (string) - Unique ID
- type (string) - Identifier (Movie or TV Show)
- title (string)
- director (string)
- cast (string) - CSV
- country (string) - Country where it was produced
- date_added (string) - Date added on Netflix (e.g. September 25, 2021)
- release_year (int)
- rating (string) - TV Rating (e.g. PG-13)
- duration (string) - Duration in minutes or seasons (e.g. 90 min, 2 Seasons)
- listed_in (string) - Genre CSV
- description (string) - Summary description

## The Movies Dataset

https://www.kaggle.com/datasets/rounakbanik/the-movies-dataset

These files contain metadata for all 45,000 movies listed in the Full MovieLens Dataset. The dataset consists of movies released on or before July 2017. Data points include cast, crew, plot keywords, budget, revenue, posters, release dates, languages, production companies, countries, TMDB vote counts and vote averages.

This dataset also has files containing 26 million ratings from 270,000 users for all 45,000 movies. Ratings are on a scale of 1-5 and have been obtained from the official GroupLens website.

This dataset consists of the following files:

**credits.csv (189.92 MB):** Contains Cast and Crew Information for all movies in the movies_metadata.csv file. Available in the form of a stringified JSON Object.
- cast (string)
- crew (string)
- id (int)

**keywords.csv (6.23 MB):** Contains Cast and Crew Information for all movies in the movies_metadata.csv file. Available in the form of a stringified JSON Object.
- id (int)
- keywords (string)

**links.csv (989.11 kB):** Contains IMDB and TMDB IDs of all movies featured in the ratings.csv file (About 45,000 movies).
- movieId (int)
- imdbId (int)
- tmdbId (int)

**movies_metadata.csv (34.45 MB):** The main Movies Metadata file. Contains information on 45,000 movies featured in the Full MovieLens dataset. Features include posters, backdrops, budget, revenue, release dates, languages, production countries and companies.
- adult (bool)
- belongs_to_collection (string)
- budget (int)
- genres (string) - JSON object
- homepage (string)
- id (int) - ID
- imdb_id (string)
- original_language (string) - e.g. en
- original_title (string)
- overview (string)
- popularity (float)
- poster_path (string) - Relative URL
- production_companies (string) - JSON object
- production_countries (string) - JSON object
- release_date (string) - Format 1995-12-15
- revenue (int)
- runtime (float) - minutes
- spoken_languages (string) - JSON object
- status (string) - e.g. Released
- tagline (string)
- title (string)
- video (bool)
- vote_average (float)
- vote_count (int)

**rating.csv (709.55 MB):** ratings of all movies featured in the ratings.csv file.
- userId (int)
- movieId (int)
- rating (float)
- timestamp (int) - Epoch time

## Letterboxd (Movies Dataset)

https://www.kaggle.com/datasets/gsimonx37/letterboxd

All film-related metadata used in Letterboxd, including actor, director and studio names, synopses, release dates, trailers and poster art is supplied by The Movie Database (TMDb).

The data contains the following fields:

1. **movies.csv (254.43 MB)** - basic information about films
    - id (int) - movie identifier (primary key)
    - name (string)
    - date (int) - year of release
    - tagline (string) - slogan
    - description (string)
    - minute (int) - movie duration (in minutes)
    - rating (float) - average rating
2. **actors.csv (195.19 MB)** - actors who took part in the filming of films
    - id (int) - movie identifier (foreign key)
    - name (string) - actor's name
    - role (string) - character's name in film
3. **crew.csv (161.99 MB)** - film crew
    - id (int) - movie identifier (foreign key)
    - role (string) - role in the film crew (director, screenwriter, etc.)
    - name (string)
4. **languages.csv (28.6 MB)** - in what languages ​​the films were shot
    - id (int) - movie identifier (foreign key)
    - type (string) - type (primary, spoken, etc.)
    - language (string) - film language
5. **studios.csv (18.33 MB)** - film studios
    - id (int) - movie identifier (foreign key)
    - studio (string)
6. **countries.csv (10.94 MB)** - countries
    - id (int) - movie identifier (foreign key)
    - country (string)
7. **genres.csv (17.93 MB)** - film genres
    - id (int) - movie identifier (foreign key)
    - genre (string)
8. **themes.csv (5.56 MB)** - themes in films
    - id (int) - movie identifier (foreign key)
    - theme (string) - theme of the film (e.g. Crude humor and satire)
9. **releases.csv (51.23 MB)** - movie releases
    - id (int) - movie identifier (foreign key)
    - country (string) - release country
    - date (string) - release date with format 2023-07-21
    - type (string) - release type (theatrical, television, etc.)
    - rating (string) - age rating (e.g. PG)
10. **posters.csv (94.87 MB)** - movie posters
    - id (int) - movie identifier (foreign key)
    - link (string) - URL

**Notes**:
1. All files are "exploded" meaning there is the same primary `id` multiple times. For example, a film may have been released in multiple countries or dubbed in multiple languages. Each has its own record.
2. **tagline** (film slogan) is present only in relatively modern films.
3. **rating** (average film rating) is missing for most films, since most likely there is not a sufficient number of estimates to calculate it.
4. If the value of **type** (movie language type) is Language, means the language is both primary and spoken (Primary language and Spoken language).
5. Some films do **not have a poster**