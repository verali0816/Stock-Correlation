---
layout: page
excerpt: "So Simple is a responsive Jekyll theme for your words and images."
---
<h1>Change of Correlations of S&P 500 Stocks in 2008-2016</h1>
<h2>Correlation Filtering Network</h2>
To build the correlation network from year 2008 to 2016, we used the correlation matrix. Two stocks with absolute correlation larger than 0.6 are connected with an edge. Below is the networks in this nine years,

Figure 1. Correlation Network from year 2008 to 2016.
<figure class="third">
	<img src="https://github.com/verali0816/aiyamaya/blob/master/images/corr_2008_m2.png?raw=true" alt="image">
	<img src="https://github.com/verali0816/aiyamaya/blob/master/images/corr_2009_m2.png?raw=true" alt="image">
	<img src="https://github.com/verali0816/aiyamaya/blob/master/images/corr_2010_m2.png?raw=true" alt="image">
</figure>
<figure class="third">
	<img src="https://github.com/verali0816/aiyamaya/blob/master/images/corr_2011_m2.png?raw=true" alt="image">
	<img src="https://github.com/verali0816/aiyamaya/blob/master/images/corr_2012_m2.png?raw=true" alt="image">
	<img src="https://github.com/verali0816/aiyamaya/blob/master/images/corr_2013_m2.png?raw=true" alt="image">
</figure>
<figure class="third">
	<img src="https://github.com/verali0816/aiyamaya/blob/master/images/corr_2014_m2.png?raw=true" alt="image">
	<img src="https://github.com/verali0816/aiyamaya/blob/master/images/corr_2015_m2.png?raw=true" alt="image">
	<img src="https://github.com/verali0816/aiyamaya/blob/master/images/corr_2016_m2.png?raw=true" alt="image">
</figure>

As we can see in the above graphs, the networks are becoming more disconnected and there are more distinct modules over time. Before 2011, the US economy was under financial crisis. Meanwhile, the networks form a few modules and the nodes are highly correlated. After 2011, the US economy was under recovery. The networks form more diversified modules and the nodes are less correlated. The labeling of nodes represent the sector information of that stock. We observed that the modularities are somewhat consistent with the sector information. 

<h2>Analysis of Network</h2>
Figure 2 clearly illustrates the changes in the number of modules in network from year 2008 to 2016. After 2011, there was an significant increase in the number of modules. 

Figure 2. The number of modules in network from year 2008 to 2016.

<iframe width="400" height="300" frameborder="0" scrolling="no" src="https://plot.ly/~wqli0816/32.embed"></iframe>
    

Reversely, the average degree of all the nodes in these nine year changed in another direction. Figure 3 shows that the average degree decreased after 2011. 

Figure 3. The degree average of nodes from year 2008 to 2016. 

<iframe width="400" height="300" frameborder="0" scrolling="no" src="https://plot.ly/~wqli0816/28.embed"></iframe>
    

To study the evolution of degree distribution over these 9 years, we plotted the degree histogram for each year. In Figure 4, You can click on or off each specific year to view or close the degree histogram for that year. Specifically, from 2008 to 2011, the distribution of degrees shift to the right, indicating there are more nodes with higher degrees, suggesting higher connectivity to neighbouring nodes. After 2011, the distribtution of degrees shift to the left, indicating there are more nodes with less degrees, suggesting lower connectivity to neighbouring nodes.

<iframe width="600" height="400" frameborder="0" scrolling="no" src="https://plot.ly/~wqli0816/22.embed"></iframe>

We also studied the changes in connectivity of stocks in each sector over time. We selected two biggest sectors, Consumer Discretionary and Information Technology, to illustrate (Figure 5). The size of circles represent the average degree of stocks in that sector in different modules. These two sectors gave similar conclusion. Before 2011, the stocks for each sector were distributed in less modules but had higher average degree. In contrast, after 2011, the stocks for each sector were distributed in more modules but had lower average degrees. 

Figure 4. The distributions of stocks in two sectors in 2008 to 2016. 
<figure class="half">
	<img src="https://github.com/verali0816/Stock-Correlation/blob/master/images/Consumer.png?raw=true" alt="image">
	<img src="https://github.com/verali0816/Stock-Correlation/blob/master/images/IT.png?raw=true" alt="image">
</figure>

# Trend Visualization among Sectors


<h1>Portfolio Selection Based on Minimum Spanning Tree</h1>
<h2>Minimum Spanning Tree</h2>
<p>Minimum Spanning tree is a common method to filter out complex network by maximizing the sum of correlations over connections in graph.  We adopted Prim's algorithm by <a href = 'http://peekaboo-vision.blogspot.com/2012/02/simplistic-minimum-spanning-tree-in.html'> Peekaboo </a> to build our network of S&P 500 stocks.</p>
<strong>Schematising of Minimum Spanning Tree:</strong><br>
<ul><li>1. rank a couple of vertices(stocks) from the nearest to the farthest</li>
<li>2. draw the first edge from this rank</li>  
<li>3. continue in the rank</li>  
<li>4. if the new edge does not close a cycle draw it</li>  
<li>5. go to point 3</li>  
<li>6. stop when all the vertices have been drawn</li></ul>  
<p>We use the distance matrix defined as following to construct the network.<br>
<div lang="latex">distance_{i,j} = \sqrt{2.0 * ( 1 – correlation_{i, j}}</div><br>
 try \\( distance_{i,j} = why \\)

this try \\( 1/x^{2} \\)
why \\[ \frac{1}{n^{2}} \\]

<h2>Portfolio Selection</h2>
<p>We want to buld to portfolio, central portfolio and peripheral portfolio. The central portfolios and the peripheral portfolios represent two opposite sides of correlation and agglomeration. Generally speaking, central stocks play a vital role in the market and impose strong influence on other stocks, whereas the correlations between peripheral stocks are weak and contain more noise than central stocks.<br>
To measure centrality and peripherality of nodes in MST, we define two indecie, Centrality indes and Distance index.<br>
<ul>
<li lang="latex">Centrality index = 0.5*Degree + 0.5*Betweenness centrality</li>
<li lang="latex">Distance index = \frac{Ddegree + Dcorrelation + Ddistance}{3}</li></ul>
The five measurements above are:
<ul>
<li>Degree K, the number of neighbor nodes connected to a node. The larger the K is, the more the edges that are associated with this node </li>
<li>Betweenness centrality C, reflecting the contribution of a node to the connectivity of the network. Denote V as the set of nodes in the network</li>
Distance refers to the shortest length from a node to the central node of the network. Here, three types of definitions of a central node are introduced to reduce the error caused by a single method. Therefore three types of distances are described here. 
<li>Distance on degree criterion Ddegree, a central node is the node that has the largest degree</li>
<li>Distance on correlation criterion Dcorrelation, a central node is the node with the highest value of the sum of correlation coefficients with its neighbors</li>
<li>Distance on distance criterion Ddistance, a central node is the node that gives the smallest value for the mean distance</li><br>
Then we pick up the stocks with the first 15 largest centrality index to make up central portfolio and the stocks with the first 15 largest distance index to build peripheral portfolio.<br>

Applied the algorithm to stock data of 2015, the MST is displayed as following. The orange nodes in graph are the stocks in central portfolio and the green nodes are the stocks of peripheral portfolio</p>

<h2>Simulation of Performance of Portfolios</h2>
<p>Assume invest $100000 on the portfolio on 2016-01-01 and keep the portfolio for 1 year. As the figure shows, both the portfolios beat the market.</p>
<figure class="half">
	<img width="600" height="400" src="https://github.com/verali0816/Stock-Correlation/blob/master/images/mst_portfolio.png?raw=true" alt="image">
	<img width="600" height="400" src="https://github.com/verali0816/Stock-Correlation/blob/master/images/performance_of_portfolio.png?raw=true" alt="image">
</figure>
 

