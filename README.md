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
[src](src) (directory) – Contains python source files

	/hits.py – Implements the HITS algorithm
  
	/dataset_fetcher.py – Fetches the dataset using the Twitter API


[data](data) (directory) – Contains the structures saved after obtaining the dataset

	/adj_list – Adjacency list representing the fetched dataset
  
	/dense_link_matrix – Link matrix using non sparse representation
  
	/sparse_link_matrix – Link matrix using sparse representation
  
	/map – Map from user id to matrix index
  
	/users – Users information


[docs](docs) (directory) - Contains the documentation for the various components
	
	/dataset_fetcher.html – doc for dataset_fetcher.py
  
	/hits.html – doc for hits.py

	/requirements.txt – Contains requirements to run the python code

Usage:
------
- Download/Clone this repository
```bash
git clone https://github.com/nikhil-iyer-97/HITS-Algorithm-implementation.git
```
- Change working directory to the where the repository is located
```bash
cd HITS-Algorithm-implementation
```
- Install dependencies:
```bash
pip install -r requirements.txt
```
- Change working directory to `src`:
```bash
cd src
```
  Now enter `python3 hits.py` for the program to run and display outputs.
  
Example:
--------
Some example outputs for hubbiness scores and authority scores for the first 30 nodes in the graph are shown below:
![Hubbiness Scores](/docs/hubbiness_scores.png)
![Authority Scores](/docs/authority_scores.png)

The change in hub score and authority score with respect to a few selected entities were measured, resulting in:
![Change in Hubbiness Score vs Iterations](/docs/hubs.png)
![Change in Authority Score vs Iterations](/docs/auths.png)

And finally, the algorithm was benchmarked on Sparse Matrix vs Normal Matrix implementations for various values of <a href="https://www.codecogs.com/eqnedit.php?latex=\epsilon" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\epsilon" title="\epsilon" /></a>:

![Time taken to run HITS algorithm](/docs/stats.png)


