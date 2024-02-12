# Music Recommendation System

## High Level Architecture:
1. AudioSet Dataset
2. Embedding Generator (MAX Audio Embedding Generator)
3. Recommendation Engine (ANNOY)
4. Recommended Audios

## Learnings
1. Handling TFRecord files using tf.train.SequenceExample
2. Annoy Indexing - Approximate Nearest Neighbors
    - Used in Spotify music recommendation
    - Pick two points randomly and the splitting by the hyperlane equidistant from those two points.
    - Keep splitting each subspace recursively
    - Split until there is at most K items left in each node
    - In order to search the constructed index, the forest is traversed in order to obtain a set of candidate points from which the closest to the query point are returned
    - Annoy Usage
        - number_of_trees: the number of binary trees we build, a larger value will give more accurate results, but larger indexes
        - serach_k: the number of binary trees we search for each point, a larger value will give more accurate results, but will take a longer time to return
