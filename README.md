# Differentially Private Matrix Completion via Alternating Minimization
## Abstract
Data privacy is fundamentally important in big data analysis, machine learning and distributed systems. To guarantee practical privacy, the notion of differential privacy is adopted to maximize the accuracy of queries in statistical database while minimizing the possibility of identifying records. In the matrix completion problem, recovery accuracy and data privacy are two contradicting aspects, since revealing more entries will increase the estimation accuracy but sacrifices privacy. Thus, privacy-preserving matrix completion is a challenging issue. In this paper, we propose a novel scheme for differentially private matrix completion with provably better accuracy bound. First, we present our differential private version of the practically efficient alternating minimization algorithm. Secondly, we present theoretical results for ensuring required privacy. Thirdly, on real world data sets, we compare the performances of our scheme with that of state-of-the-art schemes.

## Project Summary
+ We use Matlab to achieve a practical approach to complete matrix. 
+ For synthetic data, we compare our Differentially Private Matrix Completion via Alternating Minimization with Private Frank-Wolf algorithm, since both are designed for low-rank matrix completion, to show the advantage of our algorithm. We conduct experiment to recover a low-rank matrix with rank-<a href="https://www.codecogs.com/eqnedit.php?latex=$&space;r&space;$" target="_blank"><img src="https://latex.codecogs.com/gif.latex?$&space;r&space;$" title="$ r $" /></a>, from observed elements in the subset <a href="https://www.codecogs.com/eqnedit.php?latex=$\Omega$" target="_blank"><img src="https://latex.codecogs.com/gif.latex?$\Omega$" title="$\Omega$" /></a>. 
+ For recovery error, we adopt the relative square metric (RSE) and root mean square error (RMSE).
+ For running time, varying the matrix size and fixing other parameters, we measure CPU time in seconds.
+ For convergence speed, we measure the decreasing rate of the RES across the iterations by linearly fitting the measured RSEs (in log scale). We include those plots due to two reasons: 1) both algorithms are iterative; 2) the decreasing speed of the RSE provides explanations for the observed performance of the recovery error and the running time.

## Algorithm
Our new algorithm are shown as follows:
![](https://github.com/hust512/DP_Matrix_Completion_Alt_Min/raw/master/Alg/Alg2.png)  
![](https://github.com/hust512/DP_Matrix_Completion_Alt_Min/raw/master/Alg/Alg3.png)  
![](https://github.com/hust512/DP_Matrix_Completion_Alt_Min/raw/master/Alg/Alg4.png)  
![](https://github.com/hust512/DP_Matrix_Completion_Alt_Min/raw/master/Alg/Alg5.png)  


## Data
As we want to preserve privacy of every user, and the output for each user is <a href="https://www.codecogs.com/eqnedit.php?latex=$n$" target="_blank"><img src="https://latex.codecogs.com/gif.latex?$n$" title="$n$" /></a>-dimensional, we expect the private recommendations to be accurate only when <a href="https://www.codecogs.com/eqnedit.php?latex=$m\gg&space;n$" target="_blank"><img src="https://latex.codecogs.com/gif.latex?$m\gg&space;n$" title="$m\gg n$" /></a>. Due to this constraint, we conduct experiments on the following datasets: 1) Synthetic: We generate a random rank-one matrix <a href="https://www.codecogs.com/eqnedit.php?latex=$\bm{M}=\bm{U}\bm{V}^T$" target="_blank"><img src="https://latex.codecogs.com/gif.latex?$\bm{M}=\bm{U}\bm{V}^T$" title="$\bm{M}=\bm{U}\bm{V}^T$" /></a> with unit <a href="https://www.codecogs.com/eqnedit.php?latex=$\ell_\infty$" target="_blank"><img src="https://latex.codecogs.com/gif.latex?$\ell_\infty$" title="$\ell_\infty$" /></a>-norm, <a href="https://www.codecogs.com/eqnedit.php?latex=$m=500K$" target="_blank"><img src="https://latex.codecogs.com/gif.latex?$m=500K$" title="$m=500K$" /></a>, and <a href="https://www.codecogs.com/eqnedit.php?latex=$n&space;=&space;400$" target="_blank"><img src="https://latex.codecogs.com/gif.latex?$n&space;=&space;400$" title="$n = 400$" /></a>, 2) MovieLens10M (Top 400): We pick the <a href="https://www.codecogs.com/eqnedit.php?latex=$n&space;=&space;400$" target="_blank"><img src="https://latex.codecogs.com/gif.latex?$n&space;=&space;400$" title="$n = 400$" /></a> most rated movies from the Movielens10M dataset, resulting in <a href="https://www.codecogs.com/eqnedit.php?latex=$m&space;\approx&space;70K$" target="_blank"><img src="https://latex.codecogs.com/gif.latex?$m&space;\approx&space;70K$" title="$m \approx 70K$" /></a> users, 3) Netflix (Top 400): We pick the <a href="https://www.codecogs.com/eqnedit.php?latex=$n&space;=&space;400$" target="_blank"><img src="https://latex.codecogs.com/gif.latex?$n&space;=&space;400$" title="$n = 400$" /></a> most rated movies from the Netflix prize dataset, resulting in <a href="https://www.codecogs.com/eqnedit.php?latex=$m&space;\approx&space;474K$" target="_blank"><img src="https://latex.codecogs.com/gif.latex?$m&space;\approx&space;474K$" title="$m \approx 474K$" /></a> users.

## Performance Evaluation
### DP_FW(Iteration-RMSE)
![](https://github.com/hust512/DP_Matrix_Completion_Alt_Min/raw/master/DP_FW/DP_FW.png) 
### DP_Altmin(Iteration-RMSE)
![](https://github.com/hust512/DP_Matrix_Completion_Alt_Min/raw/master/DP_AltMin/DP_AltMin.png) 

