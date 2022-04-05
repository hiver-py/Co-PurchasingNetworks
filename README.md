# Graph analysis of co-purchasing networks 

Using PySpark and the GraphFrames library.


## Introduction 
Graph analysis entails the analysis of networks of personas, products, etc. with exciting applications in social networks and product recommendations. Companies such as Amazon use graph analysis to recommend commonly co-purchased products, thus improving the user and shopping experience.

In this project we explore the co-purchasing behaviour to explore the following: what are the most and least popular products, which products are commonly purchased when other products are purchased, and ways to recommend products to be co-purchased with a given product. 

The Amazon product co-purchasing networks data set collected in March 2003 will be used. The data contains contains 262111 nodes and 1234877 edges and is publically available [here](http://snap.stanford.edu/data/#amazon).


## Results
![Alt Text](https://github.com/hiver-py/Co-PurchasingNetworks/blob/main/assets/graph_viz_n_200.png)

\begin{table}[H]
\centering
\caption{In degree ratio}
\begin{tabular}{|l|l|r|}
\hline
| Node | Product Name | In Degree Ratio |
| --- | ---| --- |
| 14949 | Fodor's Australia 2000 | 84.0 |
| 4429 | Harley-Davidson Panheads, 1948-1965/M418  | 80.8  |
| 33   | Double Jeopardy   | 72.2 |    
| 10519    | NOVA: Killer Quake!  | 66.8   |       
| 12771    |  Jorge Negrete  | 66.0   |      

