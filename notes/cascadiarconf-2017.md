# Cascadia R Conference 2017

[Agenda with links to slides](https://cascadiarconf.com/agenda/)

## Vinay Prasad Keynote

- In medicine new practices replace older ones
- Sometimes something we had been doing is found to be no better or worse than a prior or lesser standard of care (including doing nothing)
- 2044 articles, 66% of which concern a medical practice
	- 74% test a new practice => 77% find practice beneficial, 6% are inconclusive, 17% find the practice is not better or worse (shows New England Journal of Medicine article selection bias)
	- 27% test an established practice => 38% find practice beneficial / 40% find practice no better or worse (reversal) / 22% are inconclusive
- Nothing is reversal-proofed; medical reversals include medications, procedures, devices, etc.
- People who underwent the practice during the years it fell in favor were harmed and/or mislead
- Leads to loss of trust in medical system

## [WORKSHOP] SOLVING ITERATION PROBLEMS WITH PURRR
- http://bit.ly/purrr-cascadia
- [GitHub - cwickham/purrr-tutorial: A introduction to purrr](https://github.com/cwickham/purrr-tutorial)

## Talks

### Building ensemble machine learning algorithms in R

- Myfanwy Hopkins, Data Scientist @ Intel ([GitHub](https://github.com/myffy))
- [Slide deck](https://cascadiarconf.com/talks/hopkins_myfanwy.pdf)
- Bias/variance tradeoff is why ensembles work so well
- Models built on historical data always have a limitation when applied to data in real time
- Ensemble methods involve multiple models combined by averaging of voting
- Diversity of models is key
	- Multiple models with high correlation may not improve accuracy significantly
	- Diverse models when combined together can help to balance bias and variance to find the global minimum for reduced test set error
- Random forest is a level 1 ensemble
- Level 2 ensemble is where you have multiple models and then train a model on their predictions — predictions from model K form the K-th feature vector
- [Assesing model performance](https://cran.r-project.org/package=PerformanceAnalytics)

### Playing with a Full Deque

- [Playing with a Full Deque](https://cascadiarconf.com/talks/real.html)
- **Vectors and Deques**
	- C++ has far more data structures than R
	- Standard library has vectors
	- Vectors are contiguous memory and expanding them is expensive
	- Appending expands them
	- **Solutions**:
		- Solution 1: preallocation if you know the ultimate length of a vector (one allocation for 1m elements instead of 1m allocations)
		- Solution 2: *deques* (`std::deque <T>`)
			- if you don’t know the ultimate length
			- non-contiguous memory — cheaper to append
			- still slower than preallocation
- **Pointers and References**
	- Pointers suck
		- They can be NULL and then everything breaks
		- They have confusing awful syntax
	- References are similar to pointers
		- Only one possible value
		- Can’t be NULL
		- Less eyeball-searing syntax
- Operators (skipped)
- General Principles
	- Pick containers judiciously
	- Never make a new object when you don’t have to
	- Don’t compromise readability for performance

### esvis: An R package for effect size visualizations

- [esvis: An R package for effect size visualizations](https://djanderson07.github.io/cascadia_r_conf-slides/#1) & [GitHub pages](https://djanderson07.github.io/cascadia_r_conf-slides/#1)
- Effect sizes are defined by standardized mean differences (e.g. Cohen’s *d* and Hedges’ *g*)
- Percentage Above the Cut & Transformed PAC
- Can use Area Under the PP Curve
- Ho et al. introduced V which puts AUC in SD units makes it scale invariant and assumes respective normality (normal with respect to each other under a shared transformation)

### Prioritizing Visual Encoding in Networks

- [PDF](https://cascadiarconf.com/talks/gopal_nikhil.pdf) by Nikhil Gopal
- Perception study to evaluate noticeability of visual attributes while visually scanning a network
	- Asked users to click on the most noticeable node
	- Created a reasonably-well-performing RF model to explain predict attention based on node size, node shape, color, etc.
- Put the ML model into two R packages
	- [rDynamo](https://github.com/ngopal/rDynamo) for prioritizing visual encodings
	- [rNetVisor](https://github.com/ngopal/rNetVISOR) for generating an attention heat map
- **Limitations**:
	- designed to be used with iGraph objects
	- works best for numerical data attributes
	- underlying model assumes very small networks
	- plan to run future studies to build models for larger networks and additional tasks
	- post-hoc analysis shows linear models possible

### Introduction to sparklyr
- by Kalbi Zongo (PhD at Oregon State University)
- Four modules in Apache Spark
	- Spark SQL lets you query structured data inside Spark
	- MLlib is scalable machine learning library
	- Spark Streaming for streaming computation
	- GraphX for graphical computation
- [sparklyr](http://spark.rstudio.com/)
	- provides DBI backend to execute SQL queries & [dplyr commands](http://spark.rstudio.com/dplyr.html) directly against spark tables
	- use Spark’s distributed [ML libraries from R](http://spark.rstudio.com/mllib.html)

## Lightning Talks

* Creating R Packages at For-Profit Companies
	* [PDF](https://cascadiarconf.com/talks/brodsky_jae.pdf)
	* Uploading package to CRAN means that CRAN has the right to distribute the package in perpetuity, so SNPolisher is available for download for free but not from CRAN
* Using R for Behavioral Data: The Fun and Frustration of Factorial and Repeated-Measures ANOVAs
	* [PDF](https://cascadiarconf.com/talks/williams_amy.pdf)
* Amending Descriptive Statistics Tables with Dynamic Visualizations
	* [PDF](https://cascadiarconf.com/talks/valenzuela_steele.pdf)
* Automated User Interface Testing with R
	* [CascadiaRConf: Automated User Interface Testing with R - Google Slides](https://docs.google.com/presentation/d/1-pOUogX_jjjogR22elXm7i5dBsOJXzklPIyaRjt7PSU/edit#slide=id.g2103842f27_0_76)

