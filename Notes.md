* Table of Contents
{:toc}

## Deep Learning With Differential Privacy
[Link](https://search.library.uq.edu.au/permalink/f/tbms52/TN_cdi_arxiv_primary_1607_00133)  

[1] M. Abadi et al., “Deep learning with differential privacy,” in Proceedings of the ACM Conference on Computer and Communications Security, 2016, vol. 24–28, pp. 308–318, doi: 10.1145/2976749.2978318.


##### Properties of Differential Privacy:  
* Composability
  * All compositions are differentially private, then so is their composition  
* Group Privacy  
  * Graceful degradation of privacy guarantees if datasets contain correlated inputs (e.g. same person)  
* Robustness to auxiliary information  
  * Privacy guarantees are not affected by amy side information available to the adversary

##### Adjacent Defintion & Additive Noise
Adjacent databases: differ in a single entry  

Additive Noise: Deterministic real-valued function f: D ->, uses additive noise calibrated to f's sensitivity (S_f_), the maximum of the absolute distance |f(d) - f(d')| (adjacent inputs).  
  Example:  
    Gaussian noise mechanism (Normal Distribution): N(0, S_f_^2 * VAR^2)  
  Steps for adding additive noise:  
    1. Approximate the functionality by a sequential compostion of bounded-sensitivity functions
    2. Choosing parameters of additive noise
    3. Performing privacy analysis of the resulting mechanism  
  
### Paper's Approach
Differentially private stochastic gradient descent algorithm.  

Two components:  
* Sanitizer  
  1. Limit sensitivity by clipping norm of the gradient  
  2. Add noise to the gradient of the batch  
* Privacy Accountant  
  Role: Keeps track of privacy spending over training. Depends on noise distribution  
  
Differentially Private PCA  
  Take a random sample, treat them as vectors, normalise then add Gaussian noise to Cov Matrix then apply projection.  
  Improves model quality and reduces training time.  

Convolutional layers:  
- Potentially random convolutions ?  

Lot size has significant impact on the end result. If max number of epochs is N/L, the more epochs the more accurate. However, the larger lot, the added noise has less effect. Best lot size is sqrt(N).  

### Paper's Conclusion
PCA improves model accuracy and training performance and is quite stable. (Recommended)  
Accuracy is fairly stable over network size (small number of epochs -> larger network size)  
Training params (lot size and noise scale) have large impact.  

Different types of Literature:  
* Privacy Guarantees  
  
* Learning Algorithm  
* Class of Models  


#### This Month - September
* Graph representation
* A third of the way trhough Diff Privacy Book
* Read Dwork & Rothblum's https://arxiv.org/pdf/1603.01887.pdf, which went into more detail regarding d-e DP

##### Questions
* Many types of DP and many types of databases, what should I be focusing on?
    Choose based on model to verify , then decide if one is better than other
  * Vertex/Edge TYpes
  * Looking into different divergence mechanisms
    Send journal to everyone
## Granularity
Vertex privacy vs Edge privacy. 
In some cases, the data fields and type of data (e.g. connections vs the actual person) have varying levels of 'privacy'
For instance, in a collaboration based recommendation system - it's important to know that some person likes movie B if they liked A, but that person's details should be secret VS fully censoring one person and all their connecting 'edges'

(epsilon, delta)-DP guarantees that at probability 1 - delta privacy the loss is less than epsilon.
  Delta is cryptograhically small, inverse of any polynomial

Formulae Defintions:
M: Privacy Mechanism
x: Database
w: Parameters for input into M
Q_w_: Set of queries
q_x_: A single query
(epsilon, delta)-differential privacy: for all \delta >= 0, M(*,*) satisfies it, if for every w, M(w, *) satisfies differntial privacy
k: security parameter, how small delta can be. Cryptographically small

If w (auxiliary param) specifies a collection Q_w_ = {q : X^n -> Real}
  Call M a synoposis generator

A: Synopsis generator
  Computes answers to all queries in Q_w_
  Require a reconstruction procedure R such that for each v specifying a query q_v_ in Q_w_, require a high prob that M produces A such that using A computes accurate answers. 
  Hence the use of a synthetitc database

Divergence: Difference between distributions
  Multiple exist -> KL divergence 

## October Meeting
Look into practical side and tools
  Finsih the book

Summarise works written, so they can find which concepts understand. Map of all the points, to organise research

Graph linking concepts will be helpful
  Present to supervisors, the in-depth explanation
  Successfully present then it means that I understand

The concept linking graph
  Contact when final exam timetable and Telstra schedule out.

