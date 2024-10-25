# Movie Recommendation Shiny App

## Overview
This is a Shiny app developed as a final project for STA 523. The app provides personalized movie recommendations based on user inputs, using content-based modeling. The recommendations can be based on previously watched movies or selected preferences such as favorite genres, actors, or directors. 

The app enhances user experience with features like:
- An engaging opening animation
- Selectable background music based on different moods
- Modal dialogs that provide detailed information about recommended movies
- A "Random Movie" button for fun and exploration

## How it Works
The app is divided into two main sections, each providing a different recommendation method:
1. **Recommend by Previously Watched Movie**: Users input a movie they have enjoyed, and the app suggests similar movies based on a content-based model.
2. **Recommend by Genres/Actors/Directors**: Users specify their favorite genres, actors, or directors, and the app generates recommendations based on a hypothetical "dream movie" that incorporates these preferences.

The models leverage a dataset of 1000 movies, preprocessed using a TF-IDF (Term Frequency-Inverse Document Frequency) vectorizer, to calculate similarity scores between movies. Recommendations are generated using cosine similarity.

## Features
- **Interactive UI**: Users can switch between recommendation models using tab panels. Movie details are presented through modal dialogs with random background images for an enhanced experience.
- **Movie Overview and Exploration**: Each recommended movie has detailed information such as the director, cast, genres, release date, and more. Users can click on the names of directors, cast members, and genres to explore other similar movies. Links to movie homepages are provided where available (though some may be outdated).
- **Random Movie Generator**: A "luck draw" button provides users with a random movie suggestion for entertainment, complete with an overview and option to explore further details.
  
## Data Source
All data are stored in the `movies.csv` file. The dataset includes information such as:
- Movie titles
- Genres
- Keywords
- Taglines
- Cast and director names
- Release dates
- Budget, revenue, and popularity metrics

## Installation and Running the App
1. Clone the repository to your local machine.
   ```bash
   git clone https://github.com/yourusername/movie-recommendation-shiny-app.git
   ```
2. Ensure that you have R installed with the required packages. The key dependencies for the app are:
   - `shiny`
   - `dplyr`
   - `ggplot2`
   - `tm` (Text Mining)
   - `shinyWidgets`
   - `shinyjs`

3. Launch the app by running the `shiny.R` script from within RStudio or directly from the R console:
   ```R
   source('shiny.R')
   ```
   This will start the Shiny app and open it in your web browser.

   > **Note:** The app might take about 20-30 seconds to launch, as it first runs the movie recommendation model script (`movie_recommend_model.R`).

4. Use the app's user interface to enter your preferences and get movie recommendations!

## Files in the Repository
- **shiny.R**: This file contains the Shiny app's main code, including the UI layout and server-side logic.
- **movie_recommend_model.R**: This file contains the movie recommendation models, data processing, and feature extraction logic. It runs when the app is launched to prepare the data and calculate similarity matrices.
- **movies.csv**: The dataset of movies, used for generating recommendations.
- **project.qmd**: The project documentation, including detailed descriptions of the methods and model implementation.

