# HITS-Algorithm-implementation

The HITS algorithm is being used on the Twitter follower network to find important hubs and authorities, where good hubs are people who follow good authorities and good authorities are people who are followed by good hubs. In this 
real-life scenario, a good authority could be a popular music artist and a good hub could be a music lover who follows many accomplished artists.

Dataset
-------

The dataset can be viewed as a directed graph. Each node in the graph represents a Twitter user and an edge from user A to user B implies that A is a “follower” of B and B is a “friend” of A.

The graph consists of 500 nodes with edges between two nodes if one is a follower/friend of another. The graph is stored as an adjacency list the first time it is prepared but then converted to an adjacency matrix immediately (thus requiring 
to store a map from matrix index to user id) for repeated use with the HITS algorithm. 

File Structure
---------------
/src (directory) – Contains python source files

	/hits.py – Implements the HITS algorithm
  
	/dataset_fetcher.py – Fetches the dataset using the Twitter API


/data (directory) – Contains the structures saved after obtaining the dataset

	/adj_list – Adjacency list representing the fetched dataset
  
	/dense_link_matrix – Link matrix using non sparse representation
  
	/sparse_link_matrix – Link matrix using sparse representation
  
	/map – Map from user id to matrix index
  
	/users – Users information


/docs
	
	/dataset_fetcher.html – doc for dataset_fetcher.py
  
	/hits.html – doc for hits.py

	/requirements.txt – Contains requirements to run the python code

Usage:
------
- Download/Clone this repository
- Change working directory to the where the repository is located
- Install dependencies:
	```
	pip install -r requirements.txt
	```
  - Change working directory to `src`:
	```
	cd src
	```
  Now enter "python3 hits.py" for the program to run and display outputs.
  
  The pictorial graphs displayed after running the source code indicate the hubs score and authorities score for the first 30
  nodes in the graph.
