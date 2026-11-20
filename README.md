# ST2195 Coursework Project
Part 1 In this part, you are asked to work with the Markov Chain Monte Carlo algorithm, in
particular the Metropolis-Hastings algorithm. The aim is to simulate random numbers
for the distribution with probability density function given below,

f(x) = 1/2 exp(−|x|)

where x takes values in the real line and |x| denotes the absolute value of x. More
specifically, you are asked to generate x0,x1,...,xN values and store them using the
following version of the Metropolis-Hastings algorithm (also known as random walk
Metropolis) that consists of the steps below:

## Random walk Metropolis
1. Set up an initial value x0 as well as a positive integer N and a positive real number s
2. Repeat the following procedure for i = 1,...,N
     -  Simulate a random number x∗ from the Normal distribution with mean xi−1 and standard deviation s
     -  Compute Ratio r(x∗,xi−1) = f(x∗)/ f(xi−1)
     -  Generate a random number u from the uniform distribution between 0 and 1
     -   If u < r(x∗,xi−1), set xi = x∗, else set xi = xi−1.\
a. Apply the random walk Metropolis algorithm using N = 10000 and s = 1. Use the generated samples (x1,...xN) to construct a histogram and a kernel density plot in the same figure. Note that these provide estimates of f(x). Overlay a graph of f(x) on this figure to visualise the quality of these estimates. Also, report the sample mean and standard deviation of the generated samples (Note: these are also known as the Monte Carlo estimates of the mean and standard deviation respectively).\
\
b. The operations in part 1(a) are based on the assumption that the algorithm has converged. One of the most widely used convergence diagnostics is the so-called R value. In order to obtain a valued of this diagnostic, you need to apply the procedure below:
- Generate more than one sequence of x0,...,xN, potentially using different initial values x0. Denote each of these sequences, also known as chains, by (x(j)1 ,...,x(j)N) for j = 1,2,...,J.
-  Define and compute Mj as the sample mean of chain j as Mj = 1/N [x(j)i] for all of N.\
   And Vj as the within sample variance of chain j as Vj = 1/n [(x(j)i - Mj)^2] for all of N
- Define and compute the overall within sample variance W as W = 1/J Vj for all of J.
- Define and compute the overall sample mean M as M = 1/J [Mj] for all of J\
  and between sample variance B as B = 1/J [(Mj - M)^2] for all of J.
- Compute the estimated R value as R = squareroot(B+W/W)

In general, values of R close to 1 indicate convergence, and it is usually desired for R to be lower than 1.05.  Calculate the R for the random walk Metropolis algorithm with N = 2000, s = 0.001 and J = 4. Keeping N and J fixed, provide a plot of the values of Rover a grid of s values in the interval between 0.001 and 1.

Part 2 The 2009 ASA Statistical Computing and Graphics Data Expo consisted of flight arrival and departure details for all commercial flights on major carriers within the USA from October 1987 to April 2008. This is a large dataset; there are nearly 120 million records in total, and it takes up 1.6 gigabytes of space when compressed and 12 gigabytes when uncompressed. The complete dataset, along with supplementary information and variable descriptions, can be downloaded from the Harvard Dataverse at [https://doi.org/10.7910/DVN/HG7NV7](https://doi.org/10.7910/DVN/HG7NV7)

Choose any subset of five consecutive years(e.g.2004-2008)and use any of the supplementary information provided by the Harvard Dataverse to answer the following questions using the principles and tools you have learned in this course:\
\
a. What are the best times and days of the week to minimise delays each year?\
b. Evaluate whether older planes suffer more delays on a year-to-year basis.\
c. For each year, fit a logistic regression model for the probability of diverted US flights using as many features as possible from attributes of the departure date, the sched uled departure and arrival times, the coordinates and distance between departure and planned arrival airports, and the carrier. Visualize the coefficients across years.


