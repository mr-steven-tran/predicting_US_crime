# **Predicting U.S. Crime Rates**
    
|Authors| LinkedIn | GitHub |
|-------|----------|--------|
|Anand Ramakrishnan|||
|Nick Van Bergen|[planetvb](https://www.linkedin.com/in/planetvb/)|[nvbergen](https://github.com/nvbergen)|
|Steven Tran|[steven-tran](https://www.linkedin.com/in/steven-tran/)|[mr-steven-tran](https://github.com/mr-steven-tran)|

---

## **Table of Contents**

### Data Collection

To get started replicating our work, start with these **Data Collection** notebooks. These notebooks can be run in any order.

|Notebook|Description|
|--------|-------|
|[target_data_retrieval](code/target_data_retrieval.ipynb)|Retrieve crime data from the [United States Federal Bureau of Investigation Crime Data API](https://crime-data-explorer.fr.cloud.gov/pages/docApi). An [API key](https://api.data.gov/signup/) is required before the script can be run again.|
|[cpi_retrieval](code/cpi_retrieval.ipynb)|Retrieve Consumer Price Index data from the [United States Bureau of Labor Statistics Public Data API](https://www.bls.gov/developers/api_signature_v2.htm). An [API key](https://data.bls.gov/registrationEngine/) before the script can be run again.|
|[unemployment_rates_retrieval](code/unemployment_rates_retrieval.ipynb)| Retrieve state unemployment rate data from the [United States Bureau of Labor Statistics Public Data API](https://www.bls.gov/developers/api_signature_v2.htm). An [API key](https://data.bls.gov/registrationEngine/) before the script can be run again.|
|[AG_scrape](code/AG_scrape.ipynb)|Retrieve attorney general political affiliation from their pages maintained on Wikipedia.|


### EDA and Modeling

Once the data are collected, progress through the following notebooks in the order presented to replicate our EDA and modeling results:  

|Step|Notebook|Description|
|----|--------|-----------|
|0|[join_all](code/join_all.ipynb)|Joins each of the predictor data sources with the target data sources into one dataframe for EDA and modeling.|
|1|[EDA](code/EDA.ipynb)|We conduct exploratory data analysis to identify states where crime rates are exceptional. Further, test the time series crime data for stationarity to help guide what direction to take for modeling.|
|2|[ARIMAX](code/anand_arimax_fixed.ipynb)|Based most states' crime rates over time exhibiting stationarity at the second-order differencing level, we fit the ARIMAX model and discuss predictive performance metrics.|
|3|[RNN_LSTM_Model](code/RNN_LSTM_Model.ipynb)|**NOTE: This notebook may need to be run in Google Colab.** Because not every state's time series exhibited stationarity, we construct a Recurrent Neural Network with Long Short-Term Memory to attempt to predict crime rates in the first out-of-sample year (2021 in our case).|
|4|[Discussion_LSTM](code/Discussion_LSTM.ipynb)|We discuss the modeling results of the RNN LSTM model, including limitations and potential next steps.|

Lastly, we provide [presentation slides](slides/CrimePreds.pdf) summarizing our project.

---

### Problem Statement

We are of the opinion that current research demonstrates that person-based predictive policing is in inherently racially biased and unfairly categorizes large groups of people. As such, our goal is attempt an alternative solution that achieves: 
1) A prediction. 
2) Has applications in law enforcement. 
3) Escapes internal biases. 

[Read our **Executive Summary** here](executive_summary.md)

---
### Data

|Source|Purpose|Credentials Needed|
|------|-------|------------------|
|[United States Federal Bureau of Investigation Crime Data API](https://crime-data-explorer.fr.cloud.gov/pages/docApi)|**Target Data**: Crime counts by state by year. We selected only the 50 states and DC.|[API Key Required](https://api.data.gov/signup/)|
|[United States Bureau of Labor Statistics Public Data API](https://www.bls.gov/developers/api_signature_v2.htm)|Monthly Unemployment by state (we annualized). National CPI per month per year.|[API Key Required](https://data.bls.gov/registrationEngine/)|
|[Wikipedia (python library)](https://github.com/goldsmith/Wikipedia)|Political affiliation of state attorneys general over time.|None|


---

### **Software Requirements**
If you want to set up an environment identical to the one we used, please install the following libraries and version types:

* pandas, v 1.20.1
* NumPy, v 1.2.4
* matplotlib, v 3.3.4
* seaborn, v 0.11.1
* scikit-learn v 0.24.1

**NOTE**:
The code notebook [RNN_LSTM_Model.ipynb](code/RNN_LSTM_Model.ipynb) must be run in [Google Colab](https://colab.research.google.com/).
* [Tensorflow](https://www.tensorflow.org/install/pip) (with Keras) v 2.7.0