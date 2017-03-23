---
layout: page
excerpt: "So Simple is a responsive Jekyll theme for your words and images."
---

<figure>
	<img src="https://github.com/verali0816/aiyamaya/blob/master/images/Method.png?raw=true" alt="image">
	<figcaption><a href="https://github.com/verali0816/aiyamaya/blob/master/images/Method.png?raw=true" title="Work Flow">Work Flow</a>.</figcaption>
</figure>

The Figure above displays a summary of our methodology. 

# Data Summary

We started by web-scraping the [S&P wikipedia](https://en.wikipedia.org/wiki/S%26P_500_Index) page to get the name of the companies and the standard industrial calsssification code. The later helped us to classify the stocks into different sectors which will be ised in the visualization part. We then used the Yahoo Finance module to download the Closed Stock Price and Volume for ~250 days/year for 2008-2016. Dowloading the data takes about ~30 mins/per year, resulting in 4.5 hours period to download the data for 2008-2016. We created the Closed Price correlation matrix, and used this as a filtering method to determine relationship between the stocks. 

```
Showcase method of get_data
```

The jupyter notebook for the Data_Download is available[here]()

# Network Construction
We decided to model the stock market as a network, where companies/stocks are respresented as a node. We proceeded to use the correlation matrix as a filtering method to define the interaction and create the edges between pairs of companies.  Edges were created when the |correlation| between a stocks(i,j) >  specified_treshold. 

# Minimum Spanning Tree
