# DataChallenge_IBM_Employees

Analyzing IBM Employees and Attrition
Naveen Mirapuri

This report will analyze survey data gathered from employees across IBM to gain a clearer image about the community within the company, while also striving to better understand employee attrition and potential causes. Using information from 1,470 employees, the following will first breakdown different groups of IBM workers. These groups will serve as the foundation for dissecting the makeup of the company workforce and also provide important data to be used when analyzing important company topics such as diversity and overall satisfaction. We will end up using these groups to develop a model that predicts attrition within IBM employees and can identify the most important contributing variables. With this information, the conclusion contains a final plan for IBM’s HR team on areas of future focus and improvement. 

In order to understand the categories represented in the data and the distribution of IBM employees, I generated graphs of important descriptive variables that could be used to answer the question ‘Who is the average IBM employee?’ and perhaps just as importantly, ‘Who isn’t?’ For each of these graphs, I also felt it was important to include information on how the sub-categories relate to attrition. This would allow us to visually identify if any particular group seems to have a unique association with ultimate outcomes in staying or leaving. This is by no means a proof of causality, but rather allows us to view the data through the lens of attrition and keep the goal of our model when visualizing data. 

To visualize the information, I first created a short script in R to map the integer values to their corresponding String labels (as listed in the Kaggle dataset). I then worked in Tableau to create graphs, initially building Sunburst Charts but quickly switching to segmented bar graphs, when the pie-chart-based graph became too messy for larger data. All the graphs can be found within the Data_Visualization folder.


## ***Data Visualization***
###Note:As there is no easy way to attach TableauPublic files to Github, I have simply screenshotted the workspace and used Images

With the graphs in the folder, we can analyze a few key fields. First, lets begin with gender. It is vitally important that diversity thrive in the workplace at IBM not only for the sake of equality but because a wider-range of people means more creative and innovative products. Thus, to avoid homogenity and dreaded groupthink, diversity metrics like gender are extremely important. Despite this fact, as shown in the pie chart below and bar graph in folder, female's make up just 40% of the sample. Although the number of women at IBM is far below the 50% benchmark, their proportional distribution across jobs and departments is more promising. As can be seen in the two bar graphs below, Women are spread amongst the three departments of Research and Development, HR, and Sales fairly similar to men, with a slight weight on sales. When analyzing specific jobs, the data become more optimistic for women at IBM as well. Women are shown to be holding their own in leadership roles, working at a better than 40:60 ratio in positions as Managers, Research Directors, and Sales Executives. One glaring point, however, is the absence of women as Lab Technicians and should be a focus for HR moving forward. 

![alt text](https://github.com/NaveenM12/DataChallenge_IBM_Employees/blob/master/Data_Visualization/Department.png?raw=true)
![alt text](https://github.com/NaveenM12/DataChallenge_IBM_Employees/blob/master/Data_Visualization/Gender_By_Department.png?raw=true)
![alt text](https://github.com/NaveenM12/DataChallenge_IBM_Employees/blob/master/Data_Visualization/Job_Roles_by_Gender.png?raw=true)



Improvement Areas: Women as Labroatory Technicians, improve the performance rating metric
