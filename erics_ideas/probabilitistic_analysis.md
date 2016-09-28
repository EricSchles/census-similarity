In the `next steps` section of the repo you mentioned adding inspection on the data.  I think a great thing to include would be descriptive information at the column level.  The way I'd like to propose this is with some high level analysis and some more detailed analysis.

Keeping with the idea of being able to run command line commands and then getting information about your data I submit the following commands:

`cat dataset.csv | describe_centrality`

output:
Assuming dataset.csv has two Columns: A, B
A:
	Mean: 2.7
	Median: 2.4
	Mode: None - (no value is repeated)
	Variance: 9
	Standard Deviation: 3
	Analysis: Because the data is from a normal distributution we are more likely to trust the Mean over the Median.  For distributions that don't follow a normal distribution (or have lots of outliers) the median is a better measure of central tendency
B:
	Mean: 4.5
	Median: 2.4
	Mode: 9
	Variance: 64
	Standard Deviation: 8
	Analysis: Because the data has a lot of outliers and doesn't follow a normal distribution the Median far better represents the central tendency than the Mean.

More central tendencies could be included here, including: geometric mean, harmonic mean, weighted mean, truncated mean, midrange, midhinge, trimean, geometric median, quadratic mean, rolling mean, rolling median
References: 
* [A quick reference on mean vs median](http://www.diffen.com/difference/Mean_vs_Median)
* [A good description of central tendency and it's issues](https://en.wikipedia.org/wiki/Central_tendency)

`cat dataset.csv | describe_distribution`

output:
Assuming dataset.csv has One Column: A
A:
	This is a normal distribution.  Here are the first 7 moments:
		* First Moment (mean): 4
		* Second Moment (variance): 7
		* Third Moment (skew): 2
		* Fourth Moment (kurtosis): 1
		* Fifth Moment: 0
		* Sixth Moment: 0
		* Seventh Moment: 0
	Additionally here are the Probability Mass Function, Cumulative Distribution Function, Survival Function, Percent Point Function (Inverse CDF), Inverse survival function, hazard functions, and Moment generating function.

References:
* [Description of above functions](http://docs.scipy.org/doc/scipy/reference/tutorial/stats/discrete.html)
* [Motivation for inclusion of the hazard function](http://thestatsgeek.com/2014/03/28/interpreting-changes-in-hazard-and-hazard-ratios/)

`cat dataset.csv graphical_structure.pgm | generate_probabilistic_graph`

Assume we have 5 columns: A,B,C,D,E
What graphical_structure.pgm looks like:

```
A -> B
B -> C
B -> D
C -> D
C -> E
```

Result: Generates the probabilistic graphical model.

References:
* [checkout the notebooks at pgmpy](http://pgmpy.org/)

