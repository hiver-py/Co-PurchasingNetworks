# Graph analysis of co-purchasing networks 

Using PySpark and the GraphFrames library.


## Introduction 
Graph analysis entails the analysis of networks of personas, products, etc. with exciting applications in social networks and product recommendations. Companies such as Amazon use graph analysis to recommend commonly co-purchased products, thus improving the user and shopping experience.

In this project we explore the co-purchasing behaviour to explore the following: what are the most and least popular products, which products are commonly purchased when other products are purchased, and ways to recommend products to be co-purchased with a given product. We also make 

The Amazon product co-purchasing networks data set collected in March 2003 will be used. The data contains contains 262111 nodes and 1234877 edges and is publically available [here](http://snap.stanford.edu/data/#amazon).


## Results

### Quantitative Graph Analysis

![Alt Text](https://github.com/hiver-py/Co-PurchasingNetworks/blob/main/assets/graph_viz_n_200.png)

To explore which products are co-purchased, we calculate the ratio between the in degrees and out degrees.
If the ratio is high this means that the product is often a product that does not start the purchase, but
often something bought at the end of a purchasing session: 

| Node | Product Name | In Degree Ratio |
| --- | ---| ---: |
| 14949 | Fodor's Australia 2000 | 84.0 |
| 4429 | Harley-Davidson Panheads, 1948-1965/M418  | 80.8  |
| 33   | Double Jeopardy   | 72.2 |    
| 10519    | NOVA: Killer Quake!  | 66.8   |       
| 12771    |  Jorge Negrete  | 66.0   |      



To find mutually co-purchased products GraphFrames Motif is used. In the table below 5 co-purchased
products is showed where people who buy Product A and people who buy Product B have the Mutual
product in common:


Product Name A | Product Name Mutual | Product Name B|  
| --- | ---| --- |
|Trouble with Girls   | Starting With "I"  | The Diabetic's Brand Name Food Exchange Handbook| 
| GIRLS TO THE RESCUE BOOK | The Hidden Encyclical of Pius XI  | Pagan Kids' Activity Book |
| How to Draw Dogs   | The Existence And Attributes Of God | Cape May for All Seasons   |
| Macromedia Flash MX for Windows and Macintosh | All the Rage | Comigo - Serie Ao Vivo |                                                                     
| Live Psalms   | Red Smith on Baseball | An Atlas of Obesity and Weight Control |


### Product recommendations

Lastly, we produce product recommendations by taking the ID of a product, we use the Jaccard Index to propose other products the user may enjoy. The Jaccard Index is a measure of similarity between two nodes of the graph based on the ratio of the intersection to union of their neighbours. That is, the ratio of the number of mutual neighbours to the sum of number of neighbours per node.

We use the ID 12345, which is an Italian music album. The top 5 products according to the Jaccard Index is:

|Node} |Product Name| Jaccard Index |
| --- | ---| --- |
17238  | Q's Jook Joint                                                      | 0.2857 |
13137  | Beggar's Ride (Beggars Trilogy (Paperback))                         | 0.2857 |
12344  | The Use and Abuse of Books: De Commodis Litterarum atque Incommodis | 0.2857 |
10510  | Tristana (Easy Readers Series B/Spanish)                            | 0.1250 |

