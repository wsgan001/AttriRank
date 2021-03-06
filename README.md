# AttriRank
[![Build Status](https://travis-ci.org/ntumslab/AttriRank.svg?branch=master)](https://travis-ci.org/ntumslab/AttriRank)

AttriRank is an unsupervised ranking model that considers not only graph structure but also the attributes of nodes.

A reference implementation of *AttriRank* in the paper (please see the file - attrirank.pdf):<br>
> Unsupervised Ranking using Graph Structures and Node Attributes<br>
> Chin-Chi Hsu, Yi-An Lai, Wen-Hao Chen, Ming-Han Feng, and Shou-De Lin<br>
> Web Search and Data Mining (WSDM), 2017 <br>

## Usage

### Example
Run AttriRank on sample graph with features, using damp [0.2, 0.5, 0.8]:

    python src/main.py --damp 0.2 0.5 0.8 --inputgraph sample/graph.edgelist --inputfeature sample/graph.feature

#### Options
Check out optional arguments such as AttriRank with prior, different similarity kernels by:

    python src/main.py --help

### Inputs
Supported graph format is the edgelist:

    node_from node_to

Supported feature format is the table (Comma-Separated Values):

    node_i, feat_dim_1, feat_dim_2, ...

Default settings for graph are directed and unweighted.

### Output

A comma-separated table of ranking scores with columns: [node_id, damp1, damp2, ...]

    node_id,0.2,0.5,0.8
    0,score_1,score_2,score_3
    ...

where score_1 is the ranking score of node 0 using AttriRank with damp 0.2.

## Requirements
Install all dependencies:

    pip install -r requirements.txt

## Citing

If you find *AttriRank* useful in your research, please consider citing the paper:

    @inproceedings{Hsu:2017:URU:3018661.3018668,
         author = {Hsu, Chin-Chi and Lai, Yi-An and Chen, Wen-Hao and Feng, Ming-Han and Lin, Shou-De},
         title = {Unsupervised Ranking Using Graph Structures and Node Attributes},
         booktitle = {Proceedings of the Tenth ACM International Conference on Web Search and Data Mining},
         series = {WSDM '17},
         year = {2017},
        } 

## Miscellaneous

If having any questions about the paper, please contact us at <chinchi@iis.sinica.edu.tw>.<br> 
If having any questions about codes, please contact us at <b99202031@ntu.edu.tw>.
