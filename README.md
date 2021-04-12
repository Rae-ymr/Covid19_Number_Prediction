# ENEL645 A Deep Learning Framework for COVID-19 Outbreak Prediction
## Introduction
At Deep ImageJ we are fighting against COVID-19 by first visualizing the spread of this pandemic in real-time to understand which countries worldwide have the highest level of confirmed cases and deaths due to COVID-19. We then intend to deploy the deep learning LSTM model that will predict the rise in the number of confirmed COVID-19 cases expected in Canada in the future. The objective behind building and deploying this highly reliable deep learning model is that its predictions will help the Canadian government take the necessary lockdown measures to stop the spread of COVID-19 to flatten the curve.

## Methodology
Dataset for prediction: The publicly available John Hopkin University’s (JHU’s) COVID-19 dataset was used to develop a dashboard depicting how COVID-19 is affecting countries worldwide[5]. This JHU dataset were utilized to deploy the LSTM model which was used to predict the number of confirmed COVID-19 cases in Canada. To make our analysis easier from the JHU dataset, the data for only the last three months, January 1, 2021 to April 9, 2021 was extracted. Model will predict daily new confirmed cases, and predicted cases between March 31, 2021 to April 9, 2021 will be compared with actual value. In the report whenever we have mentioned till date, it means till March 4, 2021 the last date the data was extracted.

## Data Visualization 
To first understand the magnitude of the problem at hand, JHU’s dataset was used to develop a dashboard that illustrates the total number of confirmed COVID-19 cases and deaths worldwide to date. Bootstrap, Plotly, and Django were utilized to create this dashboard[5][15].

## Model Building And Deployment
#### Data Preprocessing
This extracted dataset was then split into training and test as well as valid datasets with a ratio of 6:2:2. 
●	Imputation - The dataset did not contain missing values so no data imputation was applied. 
●	Normalization - Min-Max scaling was utilized to normalize the data since the LSTM is very sensitive to the input data. Data normalization was performed for the training dataset only. 
#### Model deployed
Firstly, LSTM model was deployed to address this supervised regression problem[8][9][10][11][12]. The LSTM model deployed was a sequential model consisting of 5 fully connected layers, followed by 3 LSTM layers, 3 dropout layers, 1 dense output layer. The LSTM model consisted of approximately 50853 parameters and was relatively easy to train and test. Secondly, GRU model was deployed to address this. The GRU model deployed was a sequential model consisting of 5 fully connected layers, followed by 3 GRU layers, 1 dense output layer. Thirdly, Bidirectional RNN model consisted of approximately 24071 parameters, consisting of one GRU layer and tow bidirectional GRU layers.


#### Building the model: For the Bidirectional RNN model the following hyperparameters and metrics were employed: 
●	Adam was used as an optimizer with a learning rate of 0.0001
●	Tanh and Sigmoid functions was used for every gate.
●	Being a supervised regression problem, the system performance was measured using two metrics namely, the mean squared error (MSE) and R-squared. 
●	Number of epochs of 600 and a batch size of 10 were considered for training the model.
●	No callbacks were defined.

## Results and Discussion

#### Model

Figure 2: Performance and prediction by the different model
The performance of the Bidirectional RNN, LSTM and GRU model are depicted above in Figure 2. The Bidirectional RNN model shows MSE and R-squared of 0.0689 and -0.9339 respectively, which performs better than the other models.

Those three models was utilized to predict the number of confirmed COVID-19 cases in Canada between March 31, 2021 to April 9, 2021. The day 9 depicts the predicted confirmed cases in Canada and the actual value is zero. 
If you want to see code in detail please refer to the link of file in my Github profile.







