# Differential Privacy Tools
#### General Analysis Articles
* [Haeberlen, Piece & Narayan (2011) (analysis of PINQ, Airavat and introduction of Fuzz)](https://repository.upenn.edu/cis_papers/609/)
* [Tavallaei, PINQuin (analysis of PINQ, Airavat, Fuzz, GUPT and introduction of PINQuin)](https://odr.chalmers.se/bitstream/20.500.12380/176660/1/176660.pdf)
### Google's Differential Privacy Tool
[Github Link](https://github.com/google/differential-privacy/)
Notes:
 * Created in 2019
 * Supports a variety of algorithms with customisable mechanisms (Laplace, Gaussian mechanisms and thresholding)
 * Uses Bazel
 * Assumes that the database has already been aggregated
    * In most cases, databases assume that only one record is associated with one real-world entity - however, this is not always the case. Having multiple records refer to same entity reduces the privacy guarantee.
    * [Wilson, Zhang, Lam, Desfontaines, Simmons-Marengo & Gipson (2019)](https://arxiv.org/pdf/1909.01917.pdf) gives a Query Engine design to mitigate this, which Google's system requires

### PINQ
[Microsoft Download Link](https://www.microsoft.com/en-us/research/project/privacy-integrated-queries-pinq/)
Notes:
 * One of the longest running Differential Privacy Query Engines
 * PINQ = Privacy INtegrated Queries is LINQ based (declarative language like SQL)
 * Creator Frank McSherry is still active in the Differential Privacy community
 * Still named as a "Prototype"
 * Haeberlen et al. names PINQ as vulnerable to Timing Attacks, State Attacks and Privacy Budget Attacks

### Airavat
[Introduction Paper (Roy, Setting, Kilzer, Shamtikov & Witchel, 2010)](https://www.usenix.org/legacy/events/nsdi10/tech/full_papers/roy.pdf)
Notes:
 * MapReduce-based
 * For distributed systems
 * Calculated sensitivity of dataset in advance, so safe from Privacy Budget Attacks and has sufficient counter measures against Timing Attacks. 
 * However, Airavat is weak to queries that attempt to change values, can return an error with too much information regarding whether the content is differentiaially private or not (Haeberlen)

## Deprecated/Retired Tools
### Uber's Differential Privacy TOol
[Github Link](https://github.com/uber-archive/sql-differential-privacy)  
Notes:
 * Created in 2017, deprecated in 2019
 * Reproducibility Error reported by [Frank McSherry](https://github.com/frankmcsherry/blog/blob/master/posts/2018-02-25.md)
