# TFG_fisica
My Bachelor in Physics Final Project

This repository includes the code of my Final Project, along with the data files that were used to gather the data to be processed and analized throughout the code.

The code is divided in five sections:

1. Imports: In this section, necessary packages are installed and libraries are imported for later use.
2. Data gathering: This section involves collecting data from three different files, selecting relevant columns, and adding information about exoplanets to the stars dataframe.
3. Data processing: Missing values in the data are handled in this section, and columns are transformed to change units and include logarithmic representations of the mass. Additionally, the distribution of planet masses is analyzed, leading to the splitting of data into two dataframes based on planet masses (below and above 40 Earth masses). The planet masses-host star metallicity diagram is represented for each dataframe, and at first sight a positive correlation is observed for light planets.
4. Bootstrap: In this section, the Spearman correlation between variables is studied using a simulation that incorporates the Bootstrap resampling technique (consists in taking a random sample with replacement from the original data). This accounts for errors in variables and the presence of planets (those discovered by transit methods) with unknown mass, where only minimum mass data is available.
5.  This section focuses on estimating the correlation using the MCMC algorithm, specifically the Hamiltonian Monte Carlo (HMC) algorithm implemented by the probabilistic software Stan. It consists of four subsections: in the first one, the simplest model is used to estimate correlation, neglecting errors in planet mass and star metallicity variables, as well as the presence of minimum mass data. In the second one, investigation is conducted to determine if robust correlation techniques (assuming a multivariate Student's t-distribution instead of a multivariate normal distribution for the variables) are necessary. It is concluded that this approach is not required. In the third one, correlation is estimated accounting for the errors associated with the variables of interest. And finally, in the last one, correlation is estimated considering the errors and treating the situation of minimum masses. 

Based on all the analysis, the conclusion is that there is a moderate positive correlation between exoplanets with masses below 40 Earth masses and the metallicity of their host stars. In contrast, for exoplanets with masses above 40 Earth masses, the correlation is weak and negative.
