Abstract

The importance of the construction industry to the Irish economy highlights the necessity for a thorough understanding of its historical patterns and dynamics in order to enable informed decision-making. This study conducts a comprehensive analysis of historical data collected between 1975 and 2022, covering significant aspects such as labor force statistics, construction costs, home prices, gross value addition of the sector, and building permit numbers. 

The data was collected annually and then interpolated on a quarterly basis for a more detailed examination. To determine the value addition of gross in Ireland's construction sector in contrast to other European nations, a comparative examination is also done. By focusing on these crucial elements, this study intends to offer insightful analyses of the historical performance and comparative position of Ireland's construction sector.
The goal is to gather insightful knowledge into the long-term performance and growth of Ireland's construction business through the painstaking collection and analysis of this large dataset. The analysis probes into the underlying trends, patterns, and linkages within the data, going beyond simple numerical values.

This study used information from reliable sources, including the Central Statistics Office (CSO) of Ireland and Eustat. The reliability of the data was ensured by the data gathering procedure's adherence to these institutions' policies. To prepare the data, the Python pandas module was used. The Missingno package was used to find missing values in the dataset. In order to fill in the gaps left by missing values and provide a complete dataset, additional methods including interpolation and imputation were used.

Related datasets were merged to improve the study, giving a thorough insight of the building industry. Using Plotly Express, interactive data visualization was made possible, providing dynamic and visually appealing graphs. The Scipy library was used in statistical analysis, and Scikit-learn was used to create machine learning models.

This study evaluated the sentiment conveyed in textual data acquired from the Reddit API using sentiment analysis approaches using NLTK and TextBlob and compared the outcomes of the two methods. Particular attention was paid to debates over homelessness in Ireland, which provided insight into how the general population views the need for new housing solutions.

Thus, the goal of this assignment is to give stakeholders, decision-makers, and industry professionals a thorough, data-driven assessment of Ireland's construction industry that includes insightful recommendations. Making well-informed decisions to influence the future trajectory of the Irish construction sector requires an awareness of previous dynamics and patterns.


1. DATA PREPARATION

The raw data for our research on the construction industry came from two primary sources, the European Statistical Office and the Central Statistics Office of Ireland, as well as a class-provided alpha code dataset. These sources were chosen based on their credibility and applicability, ensuring that the research process was thorough. The specificity of data on the construction industry, which allowed for in-depth analysis, was an advantage. However, obstacles arose in the form of data gaps, which were mitigated by linear interpolation, albeit with the introduction of assumptions that should be acknowledged. Importantly, all data utilization was in accordance with the required licenses and permissions, confirming the research's ethical integrity. The acquired data is licensed under a public license.

Preparing the Data for the Gross Value Addition(GVA) across various European Countries;
I begin by loading the CSV file containing data on the annual gross value addition in European countries including Ireland. I then perform a melting operation to improve the dataset's structure for further analysis. The transformation makes the dataset more compatible with the designation of alpha-3 codes for the proper countries.

Next, I clean the dataset by removing columns that do not contribute to our analysis. The data types are then modified to facilitate mathematical computations and visualizations. In addition, I rename the column headings to make them more understandable.

To obtain a comprehensive understanding of the dataset, I inspect any missing or NaN values using the Missingno visualization tool. After identifying the locations of these missing values, I determine to interpolate to generate a synthetic dataset. When it is necessary to fill in data voids, interpolation proves to be an effective technique. I, therefore, eliminate any remaining missing values from the dataset. The dataset is prepared and available for further analysis.

1.1.Missingno Visualisation
(Before Linear Interpolation)


 ![image](https://github.com/kgntmr/CONSTRUCTION-SECTOR-ANALYSIS/assets/126175253/37a446ad-d13a-4267-a532-eda74f75392b)







1.2.Missingno Visualisation
(After Linear Interpolation)

![image](https://github.com/kgntmr/CONSTRUCTION-SECTOR-ANALYSIS/assets/126175253/931e8938-2a46-49cc-abbf-5d4b9fd58109)

 

1.3. Testing, Optimisation and Documentation

Python Code Documentation, Missing Data Visualization Purpose
This code visualizes missing data in a dataset using the Missingno and Plotly Express libraries. It generates a correlation matrix plot to identify missing data patterns between columns. To utilize the provided code for missing data visualization, follow these steps:

•	Install the required libraries, namely Missingno and Plotly Express.

•	Import the libraries at the beginning of your code.

•	Define the "display_missing" function, which accepts a dataset as input.

•	Inside the function, convert any Period objects in the dataset to strings using a lambda function.

•	Within the function, generate a correlation matrix plot using "plotly.express.imshow".

•	Customize the plot's appearance by employing appropriate functions from "plotly.express".

•	Display the plot using "plotly.express.show".

•	Invoke the "display_missing" function, passing the dataset as an argument.


Conclusion:
Code performance is optimized by profiling for bottlenecks(at the end of the notebook) and applying improvements such as algorithmic enhancements, and memory management.
This code provides a concise way to visualize missing data in a dataset. It generates a correlation matrix plot, enabling the identification of missing data patterns for analysis and decision-making.


1.4. Data Preparation for Ireland’s Construction Sector Factors

This section investigates the key factors that have a significant impact on the Irish construction industry. The primary objective is to identify and meticulously examine these significant factors in order to cast light on their significant impact on the Irish construction industry. In order to achieve this, a meticulous data preparation process is essential. The following datasets will be utilized:

•	Number of Planning Permissions Granted for All Types of Construction in Ireland
•	Pricing Data for New and Second-Hand Houses in Ireland
•	Employment Statistics for Individuals aged 15 years and above in the Construction of Buildings sector
•	House Building Costs (adjusted from 1991=100 to 1975=100)
•	Census Population Data
•	Gross Value Added from the Construction Sector in Ireland

Several crucial stages were involved in the data preparation process to ensure the accuracy and dependability of the findings. This section describes the techniques used to handle absent values and optimize datasets for analysis within the context of the Irish construction industry.

Initially, the identification and processing of missing values were accomplished again with the Missingno library, a valuable instrument for visualizing and analyzing patterns of missing data. This allowed for a thorough comprehension of the extent and distribution of absent values across the datasets.

In order to effectively resolve the missing values, a common technique known as linear interpolation and iterative imputation was utilized. This method estimates the missing values based on the values of adjacent data points, presuming that they have a linear relationship and impute the data to make a synthetic dataset. By filling in missing data with estimated values, the integrity of the dataset was preserved, allowing for more accurate analysis.

In addition, the data types within the datasets were investigated and modified as required. Specifically, numeric values that were originally separated by commas were converted to integer or float data types. This transformation was performed using regular expression ("Regex") techniques, enabling a standardized and consistent format across the entire dataset.

Additionally, special consideration was given to the data's temporal component. Instead of annually, the year column was interpolated on a quarterly basis. This decision was made to account for potential seasonal variations and provide a more nuanced comprehension of the data. By displaying the data on a quarterly basis, the analysis may disclose periodic trends and fluctuations in the Irish construction industry.

The organized and cleansed data frames were merged into a comprehensive dataset to facilitate further analysis and guarantee data integrity. This procedure of merging datasets allowed for a comprehensive examination of the factors influencing the Irish construction industry. The merged dataset offered a sound basis for subsequent statistical analysis and modelling.
By implementing these data preparation techniques, the study intended to improve the quality and dependability of the dataset, allowing for a more precise and insightful analysis of the significant factors affecting the Irish construction industry.

The new merged data frame is ready for further analysis and it is about the factors of Ireland’s construction sector. Prior to the introduction of the euro currency in Ireland, current currency values were converted to their respective euro equivalents.

•	Year: The year and quarter when the data was recorded (ordinal string type).
•	Construction Permission: The number of construction permissions granted (numerical, ratio type).
•	House Construction Cost: The cost of house construction (numerical, ratio type).
•	Ireland Population: The population of Ireland at the recorded time (numerical, ratio type).
•	Labour Force: The size of the labour force in Ireland (numerical, ratio type).
•	GVA in IE: Value Addition in Gross of Construction Sector in Ireland(numerical, ratio type). This column is the priority and null values are deleted according to this column and other columns are already interpolated.
•	New House Prices in IE (€): The prices of new houses in Ireland (numerical, ratio type).
•	Second Hand House Prices in IE(€): The prices of second-hand houses in Ireland (numerical, ratio type).


2. STATISTIC

The initial data frame was subjected to data imputation and linear interpolation techniques to resolve missing values effectively. Utilizing sophisticated algorithms, the imputed values were generated with precision. It is crucial to recognize that the subsequent analysis and interpretation will be performed using this imputed data, which includes synthetically derived values for the previously absent entries. Statistics will be applied particularly to European nations, with a focus on their gross value addition in the construction industry.

2.1.Paired T-statistic

Paired T-Statistic analysis was conducted to evaluate the means of two related groups. Due to the presence of multiple countries in the dataset, the Pingouin library was utilized to execute pairwise t-tests with Ireland as the focus of attention.

Despite the dataset's non-normal distribution, pairwise t-tests were conducted to determine the extent of their deviation from normality. This method was chosen to obtain insight into the potential impact of non-normality on the analysis results, thereby addressing the findings' robustness and applicability.

•	Contrast: The comparison being made between two countries.
•	A, B: The countries being compared.
•	Paired: Indicates whether the t-test is paired or not (in this case, it is False. When "paired" is set to False, it means that the samples are independent, and there is no inherent pairing or matching between them.)
•	Parametric: Indicates whether parametric t-tests were used.
•	T: The t-statistic value(Measure of the difference between the means of two groups in a t-test)
•	Dof : Degrees of freedom.
•	Alternative: The alternative hypothesis (two-sided in this case).
•	p-unc: The uncorrected p-value.
•	p-corr: The corrected p-value after applying Bonferroni correction.
•	p-adjust: The adjusted p-value using the Bonferroni correction.
•	BF10: Bayes Factor, providing evidence for or against the alternative hypothesis.
•	Hedges: Effect size measure (Hedges' g).

After conducting the test a new data frame is generated to categorize the p-corrected values into three categories: "Highly Significant," "Significant," and "Insignificant." This categorization aims to provide a categorical perspective, facilitating a clearer understanding of the significance levels associated with the analyzed data.



2.2. Paired T-Statistic Significance
(Most of the result is Insignificant due to distribution difference)


 ![image](https://github.com/kgntmr/CONSTRUCTION-SECTOR-ANALYSIS/assets/126175253/1bd3887d-212f-4fa9-a8e8-1e9902319de1)


2.3. ANOVA

The one-way ANOVA test was performed using the dataset's 'Ireland,' 'Norway,' 'Belgium,' 'Netherlands,' and 'Portugal' features. These features represent the construction sector values for each country. And they are chosen at random based on their geographic proximity to Ireland.

The F-statistic of 70.1783670124764 indicates that the variation in construction sector values between countries is significantly greater than the variation within each country. This indicates that the performance of the construction sector in the countries under consideration differs significantly.

The highly small p-value of 4.978816246598205e-32 indicates the probability of observing such extreme differences between the groups due to chance alone. In this case, the small p-value strongly suggests that the observed differences in construction sector values are highly improbable to be the result of random variation. On the basis of the provided data set, we can conclude that there are statistically significant differences in the performance of the construction sector across countries.

In addition, it is important to note that the results for skewness and kurtosis indicate that the data frame does not adhere to a normal distribution. This suggests that relying solely on these statistical methods may not yield the most precise results. The results are shown below:

  ![image](https://github.com/kgntmr/CONSTRUCTION-SECTOR-ANALYSIS/assets/126175253/d69175e5-6fdb-47a4-b71a-e3ff52a0f8a1)



2.4. Tukey’s Honestly Significant Difference(HSD)


 ![image](https://github.com/kgntmr/CONSTRUCTION-SECTOR-ANALYSIS/assets/126175253/966fac51-5041-4cfe-8d61-b1b76e4f708a)


The analysis using the Tukey HSD test with an FWER(Family Wise Error Rate) of 0.05 revealed significant differences in means between Ireland and Belgium (-9204.0321, p < 0.05), the Netherlands (20142.2429, p < 0.05), and Norway (6737.0786, p < 0.05). However, no significant difference was observed between Ireland and Portugal (p > 0.05). These findings highlight the variations in construction sector values among the examined countries.
2.5. Wilcoxon

The Wilcoxon statistic value of 67.0 is the computed test statistic for the Wilcoxon signed-rank test performed on the 'Ireland' and 'Norway' groups in the construction industry. 

In the construction industry, the Wilcoxon test revealed a significant difference between the 'Ireland' and 'Norway' groups (Wilcoxon statistic = 67.0, p = 0.0012892335653305054). This indicates that there is a statistically significant and meaningful distinction between the two categories.

2.6. T-Test

The results of an independent t-test indicate a significant difference between 'Ireland' and 'Norway' in the construction industry. The T-statistic value of -4.5794737643612375 indicates that the mean for 'Ireland' is markedly less than that for 'Norway'. The small p-value of 9.428323600397079e-05 suggests a statistically significant difference between the two categories. Therefore, it can be concluded that 'Ireland' has a lower mean value in the construction sector than 'Norway'.


2.7. Confidence Interval for the Ireland Data

With a confidence interval of 5751.4538 to 8997.8676 for the 'Ireland' data, we can say with 95% confidence that the true population mean of the 'Ireland' data lies within this interval. This indicates that, based on the observed data, there is a high probability that the true average value of the 'Ireland' data falls between 5751.4538 and 8997.8676.


3. VISUALIZATION

The Missingno library was utilized to determine and display missing data in the dataset. Then, Plotly express was used to generate colorful, interactive graphs. 
A heatmap was used to illustrate the relationship between data points, whereas line graphs were used to depict data trends over time. 
In addition, a 'bee swarm' graph was constructed to better illustrate the evolution of the construction industry. Lastly, a histogram with blue and red colors was selected to emphasize differences in data characteristics.


3.1. Illustration of Gross Value Addition for the Construction Sector in Europe
(From 1975 to 2022, Colours are indicating the minimum to maximum with plasma)

![image](https://github.com/kgntmr/CONSTRUCTION-SECTOR-ANALYSIS/assets/126175253/2cb8c544-2e23-4898-ac0e-bb39731de3df)









3.2. Visualisation of Value Addition in Gross Data for Selected European Countries

These countries are selected randomly according to their geographical proximity to Ireland. The dataset can be used for further analysis with other countries.

3.2.1 Boxplot


![image](https://github.com/kgntmr/CONSTRUCTION-SECTOR-ANALYSIS/assets/126175253/f771cad2-c299-4b00-9a7a-2379f484fb38)
 

The boxplot reveals outliers in Ireland, while using a plain blue color to avoid color-based judgments. Norway has the highest difference between minimum and maximum values, Portugal has the lowest, and Ireland falls in the moderate range.

3.2.2. Bee Swarm Plot


![image](https://github.com/kgntmr/CONSTRUCTION-SECTOR-ANALYSIS/assets/126175253/90b00003-bcc1-4fa5-8208-fc45b109c732)
 

3.2.3. Line Chart

Every colour represents different countries. According to the line chart except for “Norway” the rest of the countries had challenges due to recession. “By January 2008, housebuilding had started to slow, and unemployment was on the rise, fueled largely by construction lay-offs. However, the most pessimistic forecast predicted the economy to grow by 2.3 per cent that year and bounce back the next, but in (Taylor, 2018)”


 ![image](https://github.com/kgntmr/CONSTRUCTION-SECTOR-ANALYSIS/assets/126175253/183ba716-f68b-4b7f-9139-1941ffb12344)


3.2.4. Heatmap


![image](https://github.com/kgntmr/CONSTRUCTION-SECTOR-ANALYSIS/assets/126175253/ec200dad-40e5-4bb3-a0b5-529fa55be138)
 

I depict these relationships using colours: green for optimum positive relationship, blue for a strong positive relationship, and yellow for a weak positive relationship.


3.3. Visualizing Construction Data in the Context of Ireland

To deal with outliers, the MinMaxScaler technique was utilized. The application of MinMaxScaler is warranted by the requirement that values be scaled between 0 and 1, which is a common requirement for both machine learning algorithms and data visualization. As there are no negative values in the context of the current analysis, this scaling procedure is especially pertinent. Using MinMaxScaler, the dataset was effectively transformed to conform to the specified range, thereby improving the data's applicability for subsequent analytical and visualization tasks.

3.3.1. Bee Swarm Plot of IE
(The interactive graphs possesses cursor focusability, enabling an in-depth examination of feature behaviors across different years.)


 ![image](https://github.com/kgntmr/CONSTRUCTION-SECTOR-ANALYSIS/assets/126175253/ff374aff-5d23-435c-9ca2-0c6f703b578a)


The bee swarm plot is useful for this research because it illustrates the distribution of the data across categories, handles overlapping data well, facilitates distribution comparisons, depicts relationships between categorical and continuous variables, and provides insights into skewness and outliers.


3.3.2. Heatmap

The heatmap reveals significant correlations between variables, with the Labour Force exhibiting the strongest positive correlation with GVA in IE and the population displaying the weakest correlation.

![image](https://github.com/kgntmr/CONSTRUCTION-SECTOR-ANALYSIS/assets/126175253/c79c1661-c79f-4c28-8af5-6caa0a1b89e4)



4. MACHINE LEARNING

![image](https://github.com/kgntmr/CONSTRUCTION-SECTOR-ANALYSIS/assets/126175253/9e113512-4afc-4849-b7e9-9789dd1aa29f)



- Multiple Linear Regression:

Good overall fit, with relatively high R2 scores on both training and test datasets. Multiple linear regression is a popular model that estimates the effect of each predictor on a target variable, thereby assisting in the identification of influential predictors. 

- Lasso Regression:

Slightly underperformed compared to linear regression, with lower R2 scores on both training and test datasets. Effective for feature selection. Lasso regression employs L1 regularization to nullify extraneous predictors, thereby enhancing model interpretability and feature selection, especially for high-dimensional datasets.

- Ridge Regression:

Similar performance to linear regression, with slightly improved R2 scores. Helps handle multicollinearity. Regularization with L2 is used in ridge regression to reduce coefficient estimates and prevent overfitting. It reduces the influence of predictors that are correlated, resulting in stable model performance. The Ridge Regression model can be used for prediction.

- ElasticNet Regression:

Slightly lower R2 scores compared to linear regression and ridge regression. Useful for datasets with many features. ElasticNet incorporates the strengths of both Lasso and Ridge, utilizing L1 and L2 penalties for feature selection and coefficient shrinkage. It is effective with datasets containing numerous predictors, including those that are irrelevant or correlated.

- Decision Tree Regression:

High R2 score on training data but lower on test data, suggesting overfitting and poor generalization. The non-parametric model of decision tree regression captures complex predictor-target interactions. It is capable of handling both categorical and numeric predictors and effectively identifies complex decision boundaries.

- PCA + Linear Regression:

Lower R^2 scores compared to other models. PCA reduces dimensionality but may result in some loss of information.

4.1. Histogram of Test and Train Score Comparison 


![image](https://github.com/kgntmr/CONSTRUCTION-SECTOR-ANALYSIS/assets/126175253/6f18c3bd-904d-43c9-b9c2-623a86263065)


4.2. Natural Language Tool Kit and Text Blob

I will analyze the sentiment of Reddit API data, focusing specifically on discussions about homelessness in Ireland. The objective is to obtain insight into the country's housing requirements.

I will utilize two libraries for this analysis: TextBlob and NLTK. TextBlob provides a straightforward interface for sentiment analysis, whereas NLTK offers greater flexibility and configuration options.
NLTK is a comprehensive toolkit for natural language processing (NLP) duties, offering tokenization and stemming control. TextBlob prioritizes sentiment analysis with an approach that is simple and accessible.

TextBlob Sentiment Analysis: -0,078	                  
NLTK Sentiment Analysis: -0,111

NLTK analysis reveals an average sentiment score of approximately -0.1118, indicating a slightly more negative sentiment compared to TextBlob.

5. CONCLUSION

Using regression models to conduct an analysis, it has been determined that Ridge regression yields a stable and optimal score. Consequently, it can be utilized for predicting the future gross value addition in the Irish construction industry. The analysis of the heatmap reveals that the variables with the greatest impact are labor force and construction permission. Compared to other European nations, Ireland's construction sector has a relatively lower gross value addition. Moreover, remarks on Reddit indicate that the housing crisis has a negative effect on public sentiment. 

Considering its stability and optimal performance, stakeholders are advised to utilize Ridge regression for future predictions of gross value addition in Ireland's construction industry. The labor force and construction permission variables, which the heatmap analysis identified as having a significant impact, should be the focal point of strategies aimed at enhancing them and increasing value addition in the sector. According to Reddit comments, addressing the housing problem, which has a negative effect on public sentiment, requires proactive measures such as expanding affordable housing options and boosting access to housing resources. Moreover, benchmarking against other European nations with higher gross value addition in construction can provide valuable insights and suggestions for enhancing Ireland's performance in the industry. Lastly, it is essential to note that the data is synthetic.





REFERENCES

Taylor, C. (2018) The crash – 10 Years on: Scars remain amid the recovery, The Irish Times.Available at: https://www.irishtimes.com/business/economy/the-crash-10-years-on-scars-remain-amid-the-recovery-1.3338508 

Navigation (no date) Copyright notice and free re-use of data - Eurostat. Available at: https://ec.europa.eu/eurostat/about-us/policies/copyright. 

Statistical confidentiality - CSO - central statistics office (2022) CSO. Available at: https://www.cso.ie/en/aboutus/lgdp/csodatapolicies/statisticalconfidentiality/

https://github.com/kgntmr/CONSTRUCTION-SECTOR-ANALYSIS


