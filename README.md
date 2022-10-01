<h1>Classification-Using-Imbalanced-Dataset</h1>
<h2> Motivation</h2>
<p>In this project, I trained a model to be used for detecting the credit customers whose application might be rejected by the credit card company. This model can be used in the early stages of the customer applications to avoid the customers from losing credit scores. This simple application could increase the customers satisfaction which can in turn increase the credit company revenue by maintaining the credit card customers. For example, company can suggest to these customers new options such as less-demanding credit cards or less credit limit prior to the main application proceeds. Finnaly, I deployed a flask-based web application which can be found here. <br></p>
<p>
<h2>Challange</h2>
<p>The main challange in this study is that the availalble data (please find in this link) is highly imbalanced. Out of 25128 rows of data, only 121 data corresponds to the customers with rejected applications and the rest of the 25007 rows in dataset contains information of the customers whose application got accepted. As such, it is difficult to obtain a model with high prediction quality. In the current project, specific metrics (i.e., f1-score for both prediction classes) and specific approaches (i.e., <strong> undersampling </strong> and <strong>oversampling</strong>) are used to train an appropriate model for classification of this classification model.
</p> 
<h2> Data Description</h2>
<p> The corresponding dataset using in this project can be seen in this link. As can be seen, the corresponding dataset has 21 columns. The last column corresponds to the model prediction which is whehter the correponding customer has been approved or not. Out of the rest of 20 columns, I only used a portion of columns to make predictions. For example, using the application number has not statistical information about the corresponding customer status, so I do not use that column for training the model. Some of the features that have been used for training the model are applicant's family status, job title and total family number. 
</p>
<h2>Preprocessing the Data</h2>
<p>Fortunately the dataset does not contain any missing value, but it contains columns with a variety of data types. For example, the dataset has several categorical and integer data types. I used a column transformer in this project, because it will facilitate the use of pipe line in the last stages of the model production which is used in the web application.</p>  
<h2>Training the Model</h2>
<p>I used a cross validation to choose between three different models with different hyperparmater values. Using the dataset without any oversampling or undersampling, the corresponding model, is prone to only predict the output class as positive. To overcome this, I used two different methods:<br>
<ol>
  <li><strong>Undesampling the +1 class</strong> so that the number of +1 class and -1 class become similar</li>
  <li><strong>Oversampling the -1 class</strong> so that the number of +1 class and -1 class become similar</li></ol>
 <p>The corresponding results for three different training model is shown in the following model with the test data f1-score for both of the classes. As shown, only oversampling the data corresponding to -1  class resulted in the best model predictions. However, the f1-score is still not acceptable. Based on the corresponding data, I recommend the company to collect more dataset corresponding to the rejected credit card applications. Oversampling, the number of similar data rows increases which increase the variance of the model prediction (i.e., overfitting).</p>
 
  
  
 </ol></p>
