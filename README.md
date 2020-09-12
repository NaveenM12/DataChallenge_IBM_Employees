# DataChallenge_IBM_Employees

Analyzing IBM Employees and Attrition
Naveen Mirapuri

This report will analyze survey data gathered from employees across IBM to gain a clearer image about the community within the company, while also striving to better understand employee attrition and potential causes. Using information from 1,470 employees, the following will first breakdown different groups of IBM workers. These groups will serve as the foundation for visualizing the company's workforce and will also provide data to be used when analyzing important company topics such as diversity and overall satisfaction. We will end up using these groups to develop a model that predicts attrition within IBM employees and can identify the most important contributing variables. With this information, the conclusion contains a final plan for IBM’s HR team on areas of future focus and improvement. 

In order to understand the categories represented in the data and the distribution of IBM employees, I generated graphs of important descriptive variables that could be used to answer the question ‘Who is the average IBM employee?’ and perhaps just as importantly, ‘Who isn’t?’ For each of these graphs, I also felt it was important to include information on how the sub-categories relate to attrition. This would allow us to visually identify if any particular group seems to have a unique association with ultimate outcomes in staying or leaving. This is by no means a proof of causality, but rather allows us to view the data through the lens of attrition and keep the goal of our model when visualizing data. 

To visualize the information, I first created a short script in R to map the integer values to their corresponding String labels (as listed in the Kaggle dataset). I then worked in Tableau to create graphs, initially building Sunburst Charts but quickly switching to segmented bar graphs, when the pie-chart-based graph became too messy for larger data. All the graphs can be found within the Data_Visualization folder.


## ***Data Visualization***
#### Note: As there is no easy way to attach TableauPublic files to Github, I have simply screenshotted the workspace and used Images

With the graphs in the folder, we can analyze a few key fields. First, lets begin with gender. It is vitally important that diversity thrive in the workplace at IBM not only for the sake of equality but because a wider-range of people means more creative and innovative products. Thus, to avoid homogenity and dreaded groupthink, diversity metrics like gender are extremely important. Despite this fact, as shown in the pie chart below and bar graph in folder, female's make up just 40% of the sample. 
![alt text](https://github.com/NaveenM12/DataChallenge_IBM_Employees/blob/master/Data_Visualization/Gender.png?raw=true)

However, although the number of women at IBM is far below the 50% benchmark, their proportional distribution across jobs and departments is slightly more promising. As can be seen in the two bar graphs below, Women are spread amongst the three departments of Research and Development, HR, and Sales fairly similar to men, with a small bias towards sales. When analyzing specific jobs, the data become more optimistic for women at IBM. Women are shown to be holding their own in leadership roles, comprising more than their overall 40:60 ratio in positions as Managers, Research Directors, and Sales Executives. One glaring point, however, is the absence of women as Lab Technicians, which should undoubtedly be a focus for HR moving forward. Though women are underrepresented, they're attrition rate does not seem to be abnormal through visualization. 


![alt text](https://github.com/NaveenM12/DataChallenge_IBM_Employees/blob/master/Data_Visualization/Gender_By_Department.png?raw=true)
![alt text](https://github.com/NaveenM12/DataChallenge_IBM_Employees/blob/master/Data_Visualization/Job_Roles_by_Gender.png?raw=true)

Next, at the heart of our analysis, we will visualize data relating to work life. First, when looking at the data for Environment and Job Satisfaction, it is good to note that positive responses are clearly larger than negative ones, but also interesting to see that attrition only slightly increases with decreased satisfaction. This could point to attrition being driven by other factors, such as the reality that young people tend to change jobs quickly in technology-focused firms like IBM. In fact, looking at other graphs confirms this, as looking at the graph for total working years shows that the highest levels of attrition are amongst people just entering the workforce, who may still be exploring differnt opportunities and are highly likely to leave.

![alt text](https://github.com/NaveenM12/DataChallenge_IBM_Employees/blob/master/Data_Visualization/Environment_Satisfaction.png?raw=true)
![alt text](https://github.com/NaveenM12/DataChallenge_IBM_Employees/blob/master/Data_Visualization/Total_Working_Years.png?raw=true)

When looking at satisfaction, work-life balance and relationships are crucially important fields. According to the data, work-life balance has lots of room for improvement at IBM. While very few marked 'Bad', a vast majority chose the second-worst option of 'Better', and it is no surprise that this has the highest amount of attrition-positive employees. On the other hand, relationship satisfaction tells a different story. Relationship satisfaction seems to be stacked towards the positive fields with not much variance in attrition. Thus, a focus for HR going forward should be less on how workers communicate with others (this is still very important) and more on how they are able to work with themselves to create manageable situations.

![alt text](https://github.com/NaveenM12/DataChallenge_IBM_Employees/blob/master/Data_Visualization/WorkLife_Balance.png?raw=true)


# ***The Model***
# THE BELOW MODEL DESCRIPTION IS OUT OF DATE -- SEE 'R MODEL' FOLDER FOR UP-TO-DATE MODEL!
We will now move on to actually modeling attrition. To do this, I programmed a model in Python using scikit-learn to execute a random forest classifier to classify inputs as either attrition positive or negative. The details of cleaning the data and building the model are in the Python folder, but here are some key takeaways:

1. We had an accuracy of around 86 percent, which while high, was still only slightly higher than the accuracy we would have if we were to always select no. Even after attempting to account for skew, we improved only slightly. This does not mean, however, that our model is incorrect, rather we can see how it does against other values like F1 statistics for which it thrived. 

![alt text](https://github.com/NaveenM12/DataChallenge_IBM_Employees/blob/master/PythonAttritionModel/Model_Results.png?raw=true)


2. We can also see based on the importance/influence of each variable on the final outcome thanks to Random Forest. The resul: overtime was by far the most important factor in attrition. This brings up an interesting point for further study as well. Do the costs of attrition and high employee turnover outweigh overtime needs. If so, it seems as though IBM should be more flexible with overtime to allow for higher employee retention. The next two highest were stock option level and job level, indicating better opportunities for promotion and pay at other companies that IBM should also weigh against employee turnover in the future. Surpisingly, age was not as high up on the importance chart as anticipated from the graphs.

![alt text](https://github.com/NaveenM12/DataChallenge_IBM_Employees/blob/master/PythonAttritionModel/Variable_Influence.png?raw=true)


# ***Looking Forward***

This report brings to light important steps that the HR department needs to take in the future. Most pressing to the issue of attrition, overtime rules must be further investigated and scrutinized. Additionally, although much of attrition seems to be originating from outside sources, the HR department can look into promoting from within to prevent people from feeling they have a stagnant Job Level. Further, while gender was not a major factor in attrition, the analysis from the data visualization clearly shows a lack of women in the workplace, so that should also be an issue worth continuous consideration.   

Beyond the results of the data, as an aside, there are major issues with the HR survey that can be corrected to prevent the need for a majority of the data cleaning. First, variables that are shared or arbitrary, such as employee count or employee number, should be removed from the dataset. Additionally, one glaring point was that the 'performance review' metric (as depicted below) became arbirtrary because everyone was given positive responses and no criticism was reported. In order to improve, people have to be honest with another, so the department should also look into making people feel more safe to speak out and criticize one another. No one is saying you have to be Ray Dalio and be brutal with your coworkers, but everyone needs feedback and HR needs to make sure that's available.

![alt text](https://github.com/NaveenM12/DataChallenge_IBM_Employees/blob/master/Data_Visualization/Performance_Rating.png?raw=true)
