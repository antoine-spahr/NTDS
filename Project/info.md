Will your Movie get an Oscar ?

# Project Goal
The goal of this project is to predict whether a film will obtain or be nominated to an Oscar based on it's similarity with other film.

# Research Question
Write the research question(s) here

# Dataset to be used
* We use the IMDB dataset 5000-subset from Kaggle for the movies features.
* Scrapped Oscar dataset from the Oscar website.  
* Scrapped Golden Globes from the Golden Globes website

The nodes of our network will be movies and they will be connected based on their similarity. There will be 4 signals on top of those nodes, namely the __popularity__, the __vote count__, the __rating__ and the __movie duration__. The possible label to predict will be either a binary classification (__Has an Oscar__ vs __Do not have an Oscar__), or a regression (__Number of Oscar__), or another binary classification (__Nominated for an Oscar__ vs __Not nominated for an Oscar__).
The model will take advantage of the network structure to make its predictions.

# Method / Structure of the Analysis
## Data collection
Web-scraping the Oscar data

## Network Construction
Build 4 different adjacency matrix from :
* Casting Similarity : Weighted by the number of common actors/actresses
* Crew Similarity : Weighted by the number of common crew members
* Keyword (and Synopsis?) Similarity : Weighted by the number of common keyword (?)
* Type Similarity

## Network Signal Filtering
Filter out noise (high frequency) on the graph

## Machine Learning
Build a model to predict a movie's awards.

# Code Structure and order
Data preparation
  |----- jupyter notebook `Webscrapping.ipynb`
  |----- jupyter notebook `Data_merging.ipynb`

Graph construction
  |----- jupyter notbook `Adjacency matrices.ipynb`
  |----- jupyter notbook `Graph_construction.ipynb`

Graph exploration
  |----- jupyter notbook `Prior_exploration.ipynb`
  |----- jupyter notbook `Graph_exploration.ipynb`

Model construction and trianing
  |----- jupyter notbook `Machine_Learning.ipynb`
