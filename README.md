# Decision_Boundry_Formula_Adjust
Background:
Formulations are often produced out of speciciation and require additional ingredients to bring the properties back within acceptable limits. Additions can be made on a trial and error basis but machine learning models can be trained to take the baseline property of the batch and the ingredient as inputs and predict how much ingredient to add to bring the property back in spec. Some ingredients appear in many formulations that vary in their baseline property and often the ingredient's effect or potency will be a function of the baseline property. For example adding black pigment to a black paint will not change the color as much as adding the same pigment to a white paint. 

If a new formula is developed and added to the machine learning model we can use the historical data as an additional check to validate the behavior of the ingredient. Essentially we are comparing the potency predicted in the new case to the potency observed in similar formulations

Purpose of the current project: 
Develop a new QMV (define) to validate the batch adjustment model before utilization in production by flagging new data that is outside of the historical uncertanty for the data 

Method:
Fake data was generated for demonstration purposes (1.1).

The decision boundries for flagging was created by bootstrapping 1000 support vector regressions on the historical data and drawing the intial line at 95% confidence interval of all the fits. Addtionally the standard deviation of the rediduals from the median fit was calculated and added to the upper bound and substracted from the lower bound (2.1).

Use:
New data was compared to the historical boundries and flagged graphically and in a dataframe if outside the boundries. This data should be analyzed further to ensure the model is accurately predicting the effect of the ingredient for new formulations
