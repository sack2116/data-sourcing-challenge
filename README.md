# Data Sourcing Challenge#6

## Overview

This project involves preparing data for a movie recommendation system by sourcing movie reviews and related movie details from two different APIs: The New York Times API and The Movie Database (TMDb) API. The extracted data is merged and cleaned for potential use in natural language processing (NLP) applications.

### Args

- **For New York Times API:**
  - `query_url (str)`: The constructed URL used to fetch movie reviews.
  - `api_key (str)`: API key required to authenticate the request.
  
- **For TMDb API:**
  - `search_url (str)`: The URL used to search for movies by title.
  - `details_url (str)`: The URL used to fetch detailed movie information.
  - `api_key (str)`: API key required to authenticate the request.

### Returns

- **Merged and Cleaned DataFrame:**
  - A DataFrame containing movie reviews and related details, cleaned and ready for export.

## PseudoCode

### Part 1: Access the New York Times API
1. **Setup:**
   - Import necessary libraries.
   - Set up the base URL, filters, and query parameters.

2. **Retrieve Movie Reviews:**
   - Loop through 20 pages to collect up to 200 movie reviews.
   - Store the results in a list `reviews_list`.
   - Handle exceptions for missing data or rate limits.

3. **Data Processing:**
   - Convert `reviews_list` to a DataFrame.
   - Extract movie titles and keywords.

### Part 2: Access The Movie Database API
1. **Setup:**
   - Prepare search and details URLs using the TMDb API.

2. **Retrieve Movie Details:**
   - Loop through the titles list and perform GET requests to fetch movie IDs and detailed information.
   - Store results in `tmdb_movies_list`.
   - Extract relevant information like genres, languages, and production countries.

3. **Data Processing:**
   - Convert the results list to a DataFrame.

### Part 3: Merge and Clean the Data
1. **Merge DataFrames:**
   - Merge the New York Times reviews DataFrame and the TMDb DataFrame on the `title` column.

2. **Clean Data:**
   - Remove list brackets and quotation marks from specific columns.
   - Remove duplicates and reset the index.

3. **Export Data:**
   - Export the final DataFrame to a CSV file.

## Features

- **Data Extraction:**
  - Retrieves movie review data from the New York Times API.
  - Fetches detailed movie information from TMDb API.

- **Data Merging:**
  - Combines data from both APIs into a single DataFrame.

- **Data Cleaning:**
  - Removes unnecessary characters from list columns.
  - Handles missing data and duplicates.

## Requirements

- Python 3.6 or later
- Pandas library
- Requests library

## Setup

1. **Clone the Repository:**
   ```sh
   git clone https://github.com/sack2116/data-sourcing-challenge.git
