## Introduction

We aim to develop a machine learning algorithm based on deep learning techniques to identify potential successful applicants for Alphabet Soup's funding programs. Drawing from a dataset of 34,000 past recipients, we plan to identify key characteristics that contribute to venture success.

The model will predict success based on several feature variables, such as application type, industry sector, and requested funding amount. Certain variables like organizational name and identification will not be included. Due to the high variance in some of the variables, they have been grouped into an "other" category.

## Findings

We began by pre-processing our dataset, resulting in 44 feature inputs thanks to one-hot encoding. Using a neural network with two hidden layers (consisting of eight and four nodes), and applying the ReLu activation function, our initial model correctly identified successful applicants about 73.29% of the time.

To enhance the model's performance, we examined the dataset more closely and removed irrelevant or less informative variables. For instance, columns like SPECIAL_CONSIDERATIONS and STATUS were eliminated as they did not offer much insight. The INCOME_AMT variable was also discarded, as its skewed distribution made it unsuitable for analysis.

We used Keras Tuner to tune the model parameters, but despite various attempts, we couldn't surpass the initial accuracy of 73%. The models' performance metrics were as follows:

Optimal model according to Keras Tuner (activation: 'tanh', first_units: 30, num_layers: 3, units_0: 15, units_1: 30, units_2: 20): 73.04%
Initial model with fewer features (activation: 'relu', first_units: 8, num_layers: 2, units_0: 4): 73.29%
Second-best model from Keras Tuner (activation: 'tanh', first_units: 15, num_layers: 4, units_0: 25, units_1: 20, units_2: 25): 73.00%

## Conclusion

The maximum predictive accuracy we could achieve with our neural network models hovered around 73%. No model outperformed our initial attempt, supporting the notion that the eliminated variables were non-contributory.

For future work, if the INCOME_AMT data were available in a more usable format, it might serve as a valuable feature for enhancing model performance.
