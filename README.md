# SARIMAX Prediction - Price of Bitcoins

The goal of this project is to do a univariate time series prediction using a  SARIMAX model. The chosen dataset is the price of Bitcoins from 2012 until 2020. To accomplish this task the project is segmented into four different parts.

- EDA and data check
- Stationary analysis and Dicky-Fuller test
- Model creation and selection
- Prediction

The complete notebook can be accessed [here](https://nbviewer.jupyter.org/github/omglu93/serimax_prediction/blob/master/bitcoin_notebook.ipynb).

![img](/images/img1.jpg)

# EDA and data check

The exploratory analysis has a minor role in this dataset. I mainly used it to take a look at the missing data values and evaluate if I need to fill in the NaN gaps. Additionally, I used it to get a general idea of the data.

# Stationary analysis and Dicky-Fuller test

The fun starts now. Generally, AR, MA, ARIMA, SARIMA and SARIMAX models cannot be used without a stationarity check of the data. The test that I utilized is the Dicky-Fuller test. The DF test outputs a classical p-value. P-values are interpreted the same way as during any other statistical test and a value below 0.05 leads to a rejection of the null hypothesis (i.e. the time series is stationary). However, in this particular case, I had to use differentiation techniques (Auto diff, Box-Cox method) for the stationarity transformation.

# Model creation and selection

The model creation and selection is pretty straightforward (except the hyperparameters). Initially, I expected that the seasonal decomposition technique would offer more information about the input parameters. However, after checking the plot output I decided to approach the problem with the Grid Search method. The evaluation metric for the model selection was AIC (Akaike Information Criterion -> AIC=ln (sm2) + 2m/T). As a model selection tool, AIC has some limitations as it only provides a relative evaluation of the model. However, it is an excellent metric for checking the general quality of a model such as SARIMAX.

# Prediction

The selected model was then used to create a prediction for the next 12 months. 


# Dataset

The data is provided by Bitstamp (https://www.bitstamp.net/markets/btc/usd/?action=buy) 

# Requirements
- Python 2.7 or Python 3.6
- Jupyter Notebook

# License
MIT. See the LICENSE file for the copyright notice.

# References
http://users.monash.edu/~dschmidt/ModelSectionTutorial1_SchmidtMakalic_2008.pdf
https://forecasters.org/wp-content/uploads/gravity_forms/7-2a51b93047891f1ec3608bdbd77ca58d/2013/07/Kongcharoen_Chaleampong_ISF2013.pdf
