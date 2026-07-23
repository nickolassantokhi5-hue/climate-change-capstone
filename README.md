Predicting Global CO2 Emissions Using Economic and Demographic Data

Summary
I used global emissions, GDP, and population data from Our World in Data to explore emission patterns and test machine learning models that predict a country's CO2 emissions.

The Problem
CO2 emissions are one of the main causes of climate change, affecting the environment, economies, and people around the world. Understanding why emissions differ between countries and being able to make accurate predictions can help researchers and policymakers make better decisions about reducing emissions. This project looks at how economic and demographic factors relate to CO2 emissions and how well machine learning can predict them.

The Data
I used the Our World in Data CO2 and Greenhouse Gas Emissions dataset. The original dataset contained more than 50,000 rows and 79 columns, with information about countries and regions from 1750 to 2022. I removed aggregate regions such as “World” and “Europe” so the analysis focused on individual countries. The dataset also had many missing values, especially for GDP, population, and CO2 emissions in earlier years. After cleaning the data, I filled missing GDP and population values using country-specific median values.

What I Did
My goal was to predict a country's CO2 emissions using factors such as GDP, population, and other emissions-related information. I first cleaned the data and explored it through charts showing emission trends, top-emitting countries, and differences between continents. I then tested five different machine learning models: Linear Regression, Decision Tree Regression, Random Forest Regression, Gradient Boosting Regression, and K-Nearest Neighbors (KNN) Regression. I compared the models using R-squared, which measures how well a model explains the patterns in the data, and Mean Squared Error, which measures how far the predictions were from the actual values.

What I Found
The Random Forest Regressor was the strongest model, achieving an R-squared score of approximately 0.9756. This means it explained about 97.56% of the variation in the log-transformed CO2 emissions in my test data. It performed much better than Linear Regression, which had an R-squared score of 0.6576, and Gradient Boosting, which scored 0.8746.
The most important chart in the notebook is the Actual vs. Predicted CO2 Emissions graph for the Random Forest model. The predictions stay close to the diagonal line, showing that the model's predictions were generally very close to the actual values.

Fairness Check
A traditional demographic fairness check was not fully possible because this dataset contains countries rather than individual people. There are no individual-level demographic groups, such as age, race, or income brackets, to compare directly. Instead, I compared emissions patterns across continents and found major differences. North America and Asia generally had higher average annual CO2 emissions than Africa and South America. These differences are connected to factors such as industrialization, economic development, population size, and historical energy use.
This does not necessarily mean that the model itself is unfair, but it shows that countries and regions have very different roles and responsibilities in global emissions. In future work, I would compare model performance across countries with different levels of economic development to see whether the model is more accurate for some groups of countries than others.

Limits and What I Would Do Next
One important limitation is that I replaced missing CO2 and total greenhouse gas values with zero. This was a strong assumption and may not always be accurate because a missing value does not necessarily mean that a country had zero emissions. The data is also reported at the country level, so it does not show differences between cities, industries, or individuals within a country. Another limitation is that the project mainly focused on regular regression models instead of models designed specifically for data changing over time.
If I had another week, I would use more advanced methods for handling missing data, test time-series models, and include additional information such as environmental policies, energy sources, and technological development. I would also investigate which features had the greatest influence on the Random Forest predictions. The results should not be used to claim that one factor alone causes a country's CO2 emissions or to make perfect predictions about future emissions.

How to Run It
The project is contained in the Colab notebook. Open the notebook, connect to a Google Colab runtime, and run the cells from beginning to end. No additional files are needed beyond the dataset used in the notebook. The entire notebook should take approximately 5–10 minutes to run, depending on the Colab runtime.

Colab Notebook: https://colab.research.google.com/drive/1wnQl4Wd4D64MovmG3SfhG_XwngCivniE?usp=classroom_web#scrollTo=UGah_6UwI1n6 

Last notes:
I developed the project idea, chose the research goal, explored the dataset, analyzed the results, compared the machine learning models, and interpreted the findings. Google Gemini helped me with parts of the coding process in Colab, but the main ideas, goals, investigation, and conclusions were my own.
