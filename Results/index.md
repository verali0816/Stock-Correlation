---
layout: page
excerpt: "So Simple is a responsive Jekyll theme for your words and images."
---

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

Figure 2 clearly illustrates the changes in the number of modules in network from year 2008 to 2016. After 2011, there was an significant increase in the number of modules. 

Figure 2. The number of modules in network from year 2008 to 2016.
<figure class="half">
    <iframe width="450" height="400" frameborder="0" scrolling="no" src="https://plot.ly/~wqli0816/32.embed"></iframe>
    <iframe width="450" height="400" frameborder="0" scrolling="no" src="https://plot.ly/~wqli0816/28.embed"></iframe>
</figure>
Reversely, the average degree of all the nodes in these nine year changed in another direction. Figure 3 shows that the average degree decreased after 2011. 

Figure 3. The degree average of nodes from year 2008 to 2016. 

    

To study the evolution of degree distribution over these 9 years, we plotted the degree histogram for each year. In Figure 4, You can click on or off each specific year to view or close the degree histogram for that year. Specifically, from 2008 to 2011, the distribution of degrees shift to the right, indicating there are more nodes with higher degrees, suggesting higher connectivity to neighbouring nodes. After 2011, the distribtution of degrees shift to the left, indicating there are more nodes with less degrees, suggesting lower connectivity to neighbouring nodes.

<iframe width="450" height="400" frameborder="0" scrolling="no" src="https://plot.ly/~wqli0816/22.embed"></iframe>

We also studied the changes in connectivity of stocks in each sector over time. We selected two biggest sectors, Consumer Discretionary and Information Technology, to illustrate (Figure 5). The size of circles represent the average degree of stocks in that sector in different modules. These two sectors gave similar conclusion. Before 2011, the stocks for each sector were distributed in less modules but had higher average degree. In contrast, after 2011, the stocks for each sector were distributed in more modules but had lower average degrees. 

<figure class="half">
	<img src="https://github.com/verali0816/Stock-Correlation/blob/master/images/Consumer.png?raw=true" alt="image">
	<img src="https://github.com/verali0816/Stock-Correlation/blob/master/images/IT.png?raw=true" alt="image">
</figure>
