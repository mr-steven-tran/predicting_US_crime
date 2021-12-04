# A Top-Down Approach to Law Enforcement Resource Allocation.
## An AI based prediction model for use with government policy makers and private citizens. 
---
##### Nicholas Van Bergen <br> Steven Tran <br> Anand Ramakrishnan <br> General Assembly Data Science Immersive <br> Cohort 0927-Remote

# Executive Summary:

Using deep learning and time series forecasting techniques, we have developed a tool to help government leadership allocate resources (funds or law enforcement personnel) or drive policy decision making based on historical temporal data. What's more crucial here is that we wanted to make a model that disentangles itself from inherent biases prevalent in similar automated artificially intelligent policing systems. 

### Problem statement:
We are of the opinion that current research demonstrates that person-based predictive policing is in inherently racially biased and unfairly categorizes large groups of people. As such, our goal is attempt an alternative solution that achieves: <br>
1) A prediction. <br>
2) Has applications in law enforcement. <br>
3) Escapes internal biases. <br>

### Solution:
We tested two models, on two predictions, for 51 states over 42 years of annual data. We reviewed ARIMA and Recurrent Neural Network models. 

Our team has found using a Long Short Term Memory Recurrent Neural Network algorithm gave _best_ results given the low quantity of training instances that we had. We then developed the model and created a minimum viable product (mvp) for such a system.

The project is in a state that can be easily extended to include a dashboard, or be a supporting feature of some other application to measure a state government's effectiveness in deploying resources.  

### Results:
| **Metric** | **RNN Baseline** | **LSTM** | **ARIMA** |
| --- | --- | --- | --- |
| **Average MAE (violent crime)** | 0.304 | 0.458 | 0.369 |
| **Average RMSE (violent crime)** | 0.401 | 0.587 | 0.795 |
| **Average R2 (violent crime)** | 0.805 | 0.631 | -0.531 |
| **Average MAE (property crime)** | 0.201 | 0.397 | 2.243 |
| **Average RMSE (property crime)** | 0.256 | 0.526 | 4.772 |
| **Average R2 (property crime)** | 0.926 | 0.703 | 0.545 |


### Conclusion

The prototype mvp of our top-down approach has been promising. And there are benefits to using a top-down approach. However, we acknowledge that a top-down approach would not be a total and sweeping solution to the overall problem of instances of crime nor the problem of long-held racial bias in our justice system. Instead, we intend for this tool to be utilized ahead of time.  

The results show that the LSTM model still had cases that underperformed our ground truth data, however. We believe this could be remedied with more data to train on and perhaps looking at less broad time-window. That is, looking at time periods of Quarters, Months, and daily statistics to get a better sense of the time complexity baked into our model over a year's time. 
 
### Resources
#### APIs
1. [FBI](https://crime-data-explorer.fr.cloud.gov/pages/docApi)
1. [BLS](https://www.bls.gov/developers/)
1. [Wikipedia API](https://github.com/goldsmith/Wikipedia)
1. [BeautifulSoup](https://www.crummy.com/software/BeautifulSoup/bs4/doc/)

#### AI and AI Ethics Groups of interest
1. [Columbia University _Race + Data_ lecture series](https://youtube.com/playlist?list=PLRXLC-iYknE66vW3tiBHy1O5pfYmhFfEo)
1. [Columbia University _Race + Data_ resource page](https://datascience.columbia.edu/diversity/race-data-science-resources/)
1. [Data 4 Black Lives](https://d4bl.org)
1. [A.I. For People](https://www.aiforpeople.org)
1. [Stanford Open Policing](https://openpolicing.stanford.edu)
1. [Algorithmic Justice League](https://www.ajl.org)
---