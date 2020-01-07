# Will that Movie get an Awards ? <img src="Figures/oscars_img.png" alt="drawing" width="75"/>
---
## Project Goal
The goal of this project is to predict whether a film will be nominated to an Oscar or a Golden Globes based on it's similarity with other film and some features.

## Dataset used
* We use the IMDB [dataset 5000-subset from Kaggle](https://www.kaggle.com/tmdb/tmdb-movie-metadata##tmdb_5000_movies.csv) for the movies features.
* Scrapped Oscar dataset from the [Oscar website](https://www.oscars.org/oscars/ceremonies/).  
* Scrapped Golden Globes from the Golden [Globes website](https://www.goldenglobes.com/winners-nominees/)

The nodes of the network are the movies and they are connected based on their similarity. There will be 6 signals on top of those nodes, namely the __popularity__, the __vote count__, the __vote average__, the __budget__, the __revenue__ and the __movie duration__. Two others signals are present : the __number of nomination to an awards__ and __number of awards__.
The model will take advantage of the network structure to make predictions : is the movie being nominated to an awards (Oscar + Golden Globes).

## Method / Structure of the Analysis
### Data collection
Web-scraping of the Oscar and Golden Globes data.

### Network Construction
Build an adjacency matrix from the movie cosine similarity of
* Casting
* Crew
* Keywords
* Genres

### Graph exploration
The data is first explored without the network structure by checking the label balance and the spearman correlation between the features and the labels (_Awards_ and _Nominations_). Then the network structure is explored by the mean of numerical properties (number of nodes, number of edges, diameter, giant component size, number of connected component ...), plots (degree distribution, eigenvalue spectrums). The signals on the network are studied by mean of the quadratic form of those signals and graph Fourier transform (GFT). A [visualization](https://antoine-spahr.github.io/Movie-Network-Visualisation/) of the network is made using Gephi (circle pack layout on component, modularity and clustering coefficient) in order to investigate the network structure and how the labels are distributed on it.

### Machine Learning
Try three models to predict a movie's nominations for an Awards:
1. Simple Logistic Regression : model not using the network structure.
2. Laplacian graph filter + Logistic regression : model using the network structure through a filter.
3. Graph Convolutional Network : model using the network structure through graph convolution.
<br>

## Code Structure and order
* Data preparation
  <br>|----- jupyter notebook `Webscrapping.ipynb`
  <br>|----- jupyter notebook `Data_merging.ipynb`

* Graph construction
  <br>|----- jupyter notebook `Similarity matrices construction.ipynb`
  <br>|----- jupyter notebook `Adjacency construction.ipynb`

* Graph exploration
  <br>|----- jupyter notebook `Prior_exploration.ipynb`
  <br>|----- jupyter notebook `Graph_exploration.ipynb`

* Model construction and training
  <br>|----- jupyter notebook `Machine_Learning.ipynb`

## Interactive visualisation of the Network
[click here for the interactive web visualisation](https://antoine-spahr.github.io/Movie-Network-Visualisation/)

## Contributions
TO BE COMPLETED
