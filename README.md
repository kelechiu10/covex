# covex
repository for our project from Treehacks 2021
## Inspiration 
It has been more than a year since the start of the pandemic. Vaccines have been created, but shipping them has not been the most efficient. This [Bloomberg article](https://www.bloomberg.com/graphics/covid-vaccine-tracker-global-distribution/) shows that many vaccines are being distributed, but not actually being administered. This is concerning because vaccines have a shelf life which means that any unused vaccines would just be wasted while other distribution sites could have administered more vaccines. 

## What it does
Given time-series data about how many doses of the vaccine have been administered, CoVEx: 
<ol>
<li>Predicts and quantifies uncertainty of how many doses will be needed in the next weeks.
</li>
<li>Computes the optimal distribution throughout hospitals such that there is over a 99.9% chance that even if a hospital runs out of doses, a hospital within 15 kilometers will have doses to offer.
</li>
</li>Displays the optimal distribution on the map and predicts which hospitals will be aiding others.
</ol>

## How we built it
We gathered public vaccine distribution data to train the predictive model. By quantifying the uncertainty measures and vectorizing our constraints, we were able to formulate vaccine distribution as a convex optimization problem. Thus, we can solve these problems fast using the cvxpy library.

## Challenges we ran into
The scarce amount of publically available vaccine data meant we could not use it to model any county-level hospital interactions. To solve this, we had to develop a realistic, data-informed synthetic data set that would serve as a case study. In addition, we had to learn a data visualization API from scratch.

## Accomplishments that we're proud of
Our algorithm is concise and computes solutions given new parameters in a few seconds. Our visualization provides a roadmap to quickly understand vaccine allocation and prepare for where vaccines may need to be transferred. The model drastically reduces the number of vaccines needed while guaranteeing that no hospital will run out.

## What we learned
- Visualization can be a very time-consuming task even after your data is processed
- Understanding and using popular data science libraries such as NumPy and pandas

## What's next for CoVEx
- Obtaining more detailed data to increase prediction certainty and create better simulations.
- Making the algorithm more accurate by decentivising transportation of the vaccine between hospitals, thus adding a trade-off between cost and ease of application.
