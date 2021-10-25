# Glossary

### Additive Noise
Deterministic real-valued function f: D ->, uses additive noise calibrated to f's sensitivity (S_f_), the maximum of the absolute distance |f(d) - f(d')| (adjacent inputs).  
  Example:  
    Gaussian noise mechanism (Normal Distribution): N(0, S_f_^2 * VAR^2)  
#### Steps for adding additive noise:  
1. Approximate the functionality by a sequential compostion of bounded-sensitivity functions
2. Choosing parameters of additive noise
3. Performing privacy analysis of the resulting mechanism  

### Adjacent Database
Two databases that differ in a single entry

### Differential Privacy
Guarantee that an adversary cannot tell whether a user's data was ever used/released. Publishes information that does not depend on any indivdual by injecting randomness into the data. Individual information can be refuted, hence is confidential.

##### Properties of Differential Privacy:  
* Composability  
  * All compositions are differentially private, then so is their composition  
* Group Privacy  
  * Graceful degradation of privacy guarantees if datasets contain correlated inputs (e.g. same person)  
* Robustness to auxiliary information  
  * Privacy guarantees are not affected by any side information available to the adversary


### Divergence
Difference between two different distributions. One of which is KL-Divergence.

### (epsilon-delta)-differential privacy
(epsilon, delta)-DP guarantees that at probability 1 - delta privacy the loss is less than epsilon.  
  Delta is cryptograhically small, inverse of any polynomial. 
  See [5]

### Granularity
Vertex privacy vs Edge privacy.  
In some cases, the data fields and type of data (e.g. connections vs the actual person) have varying levels of 'privacy'
For instance, in a collaboration based recommendation system - it's important to know that some person likes movie B if they liked A, but that person's details should be secret VS fully censoring one person and all their connecting 'edges'



# References
[1] Dwork & Rothblum (2014), The Algorithmic Foundations of Differential Privacy
[2] Zhang, (2021), INFS3200 Lecture 
[3] Abadi, McMahan, Chu, Mironov, Zhang, Goodfellor & Talwar [Deep learning With Differential Privacy](https://search.library.uq.edu.au/permalink/f/tbms52/TN_cdi_arxiv_primary_1607_00133)
[4] Dwork,[The Promise of Differential Privacy: A Tutorial on Algorithmic Techniques](https://ieeexplore-ieee-org.ezproxy.library.uq.edu.au/document/6108143)
[5] Dwork & Rothblum (2016), [Concentrated Differential Privacy](https://arxiv.org/pdf/1603.01887.pdf)
  Detail on e-d differential privacy
