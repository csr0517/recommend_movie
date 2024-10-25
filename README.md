# Movie Recommendation Shiny App

## Overview
This is a Shiny app developed as a Movie Recommendation Shiny App. The app provides personalized movie recommendations based on user inputs, using content-based modeling. The recommendations can be based on previously watched movies or selected preferences such as favorite genres, actors, or directors. 

The app enhances the user experience with features like:
- **Engaging UI**: An opening animation and selectable background music.
- **Selectable Background Music**: Users can choose from multiple music tracks based on their mood, such as love, discovery, suspense, and joy.
- **Detailed Modal Dialogs**: Information about the recommended movies, including director, cast, genre, release date, and more.
- **Random Movie Feature**: A "Random Movie" button for fun and exploration, providing a random movie suggestion with details.

## How it Works
The app is divided into two main sections, each providing a different recommendation method:
1. **Recommend by Previously Watched Movie**: Users input a movie they have enjoyed, and the app suggests similar movies based on a content-based model.
2. **Recommend by Genres/Actors/Directors**: Users specify their favorite genres, actors, or directors, and the app generates recommendations based on a hypothetical "dream movie" that incorporates these preferences.

The models use a dataset of 1000 movies, preprocessed using a TF-IDF (Term Frequency-Inverse Document Frequency) vectorizer to calculate similarity scores between movies. Recommendations are generated using cosine similarity.

## Features
- **Interactive UI**: Users can seamlessly switch between recommendation models using tab panels. Movie details are displayed in modal dialogs with random background images, enhancing the user experience.
- **Music Selection**: Users can choose background music from various themes such as:
  - *Cornfield Chase*
  - *Love in Paris*
  - *Suntan Oil*
  - *Suspense Piano*
  The music plays in the background as users explore the app and can be paused or changed anytime.
  
- **Movie Exploration**: Recommended movies include clickable links for further exploration of similar movies based on the director, cast, or genre. Some movie homepage links are also provided (note: some may be outdated).
- **Random Movie Generator**: A "luck draw" button offers users a randomly selected movie, providing an overview with the option to explore more details.

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

4. Use the app's user interface to input your preferences and receive movie recommendations!

## Files in the Repository
- **shiny.R**: Contains the Shiny app's main code, including the UI layout and server-side logic.
- **movie_recommend_model.R**: This file contains the movie recommendation models, data processing, and feature extraction logic. It runs when the app is launched to prepare the data and calculate similarity matrices.
- **movies.csv**: The dataset of movies used for generating recommendations.
- **project.qmd**: Project documentation with detailed descriptions of the methods and model implementation.
- **/www/**: Contains the background music files that enhance the user experience:
  - `cornfield-chase.mp3`
  - `love-in-paris.mp3`
  - `suntan-oil.mp3`
  - `suspense-piano.mp3`
