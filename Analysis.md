### Charity Funding Predictor Analysis
## 1. Overview:

The non-profit foundation Alphabet Soup is interested in predicting which charity fundings end up being successful. Data containing more than 34,000 organizations previously funded by Alphabet Soup and their metadata is preprocessing and fitted into a deep learning neural network.

This process utilizes two different strategies:

- a baseline, “manual” attempt in which the hyperparameters of the neural network are predefined and fitted onto the data (73% accuracy) and

- an optimized, “automatic” attempt in which the hyperparameters were systematically tested used keras tuner (79% accuracy)

## 2. Graphs:

     2.1 Baseline

  ![image](https://user-images.githubusercontent.com/100891182/185627113-e1f10bdf-726d-403a-82e6-401e9e1323e8.png)

  ![image](https://user-images.githubusercontent.com/100891182/185627134-b9279c8c-5fa3-49db-afb6-4a9dc834436f.png)

     2.2 Optimization:
     
 ![image](https://user-images.githubusercontent.com/100891182/185627391-1d7826b6-cfc0-4186-83e9-6566b83d7227.png)
     
     
![image](https://user-images.githubusercontent.com/100891182/185627407-1086ffe9-d3ab-4101-826b-63b739425de1.png)



## 3. Results:


  3.1 Data Preprocessing:
  
 * What variable(s) are the target(s) for your model?   
    
 * What variable(s) are the features for your model?  
    
 * What variable(s) should be removed from the input data because they are neither targets nor features?
    
  
The dataset removed any irrelevant information; therefore, EIN and NAME were dropped from the 
model. The remaining columns were considered features for the model. Although NAME was added 
back in the second test. CLASSIFICATION and APPLICATION_TYPE was replaced with ‘Other due to high 
fluctuation. The data was split into training and testing sets of data. The target variable for the model is 
“IS_SUCCESSFUL” and is verified by the value, 1 was considered yes and 0 was no. APPLICATION data 
was analyzed, and CLASSIFICATION’s value was used for binning. Each unique value used several data 
point as a cutoff point to bin “rare” categorical variables together in a new value, ‘Other’. Afterwards 
checked to see if binning was successful. Categorical variables were encoded by ‘pd.get_dummies().
  
       
    
    3.2 Compiling, Training, and Evaluating the Model:
    
    * How many neurons, layers, and activation functions did you select for your neural network model, and why?
    
    * Were you able to achieve the target model performance?
    
    * What steps did you take in your attempts to increase model performance?
    
Neural Network was applied on each model multiple layers, three in total. The number of features 
dictated the number of hidden nodes. 

![image](https://user-images.githubusercontent.com/100891182/185629908-3016ba44-d073-4b0d-85df-38f35bd42b44.png)


A three-layer training model generated 477 parameters. The first attempt came close at 72.9% which was 
under the desired 75%

![image](https://user-images.githubusercontent.com/100891182/185630021-06eff539-001c-48e5-8d35-da8fb89ad509.png)

![image](https://user-images.githubusercontent.com/100891182/185630080-17cfaa23-40d5-43f7-80e1-23c7f257dc64.png)


     3.3 Optimization:
     
The second attempt added ‘NAME’ back into the dataset, this time I achieved 79% which was 4% over 
target. A total of 3,298 params. 


![image](https://user-images.githubusercontent.com/100891182/185631025-e808d378-20bf-4f96-a77a-5bae2dc04984.png)


Deep learning models should have multiple layers, since it is machined based it teaches a 
computer to filter inputs through the layers to learn how to predict and classify information.


![image](https://user-images.githubusercontent.com/100891182/185631165-a6dbbb4b-0653-45c4-8a8f-7ccf057d2a96.png)



