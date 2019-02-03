# kickstarter
Predicting success of Kickstarter campaigns
(CS 5010 Project, June 2018)

#### Introduction
Kickstarter [https://www.kickstarter.com/] has grown into one of the most popular crowd-funding platforms on the web since its inception in 2009.  Over 140,000 projects have been funded thanks to the patronage of millions of Kickstarter backers. From documentaries to smart watches to card games about combustible felines (Exploding Kittens) , Kickstarter has brought to life ideas that have impacted technology, design, and pop culture. 

Out of the thousands of projects that get launched on Kickstarter every month, only a few succeed. According
to their official website, they state that the average success rate on Kickstarter is ~36%. This small number is
why it becomes very important to understand the dynamics of crowdfunding and how that plays into
determining the outcome of a project. This project envisages to predict this - That given certain attributes
about a project can we predict the success or failure of a Kickstarter campaign? And what really distinguishes a
successful campaign from a failed one? The hope is to leverage data to gain some insight into the trends and
transform it into something actionable. This analysis would be useful for creators who want to check how their
project or campaign can perform on Kickstarter before they invest time and energy in launching it on the
website. And to also be able to adjust project specs and goal which could help the maximize their chances of
success. We would expect it to be useful to people or “backers” who want to determine the outcome of
project based on its current state before they commit to donating money.

#### The Data
The Kickstarter data set that we have used for our analysis has been sourced from Kaggle.com. The dataset
called Kickstarter Projects, created by a crowdfunding enthusiast Mickael Mouille, while the raw data itself has
been collected from the original Kickstarter Platform. Our reason for choosing this dataset is driven by the fact
that crowdfunding is an industry that is rapidly expanding across the world. The industry is projected to grow
over $300 billion the next 7 years by 2025! And while its generating millions of dollars, it is bringing to life
ideas in various sectors and helping people fulfil their entrepreneurial dreams. As people move towards such
non-traditional methods of obtaining investments, there is a need for better decision making for the creators
as well as donators before time, money and energy is invested in it. Using data here can help us answer
questions in a multitude of dimensions – from the binary outcome of a project to giving us insight into social
behavior of humans, understanding what really drives human interest and how that collective interest or
“crowd behavior” leads to someone’s goal getting achieved.
The original dataset sourced from Kaggle contained 15 columns each corresponding to an attribute and roughly 378k rows in total. For our analysis, we did perform some pre-processing on the data before leveraging it to gain any insight. We have primarily focused on Kickstarter trends just in the US. 

The final data obtained consisted of 14 columns and roughly 260k rows which we stored into a pandas data frame and queries from for our exploratory analysis. 

#### Pipeline

* Pre-processing 
* Exploratory Data Analysis
* Predictve Modeling

Our exploratory data analysis yielded some interesting insights from the data such as-
* Not all Kickstarter campaigns have the same shot at success. Projects in the Dance and Theatre category experience more success compared to others. The most popular category is not necessarily the most successful one.
* Categories which do experience more success generally have a modest goal. Categories like Journalism and Tech have high goals understandably but also have the lowest odds of being successful as seen from the previous chart.

We looked at campaigns by categories further analyzing each category on the basis of specific atributes such as avg days or duration, avg backers,etc. We also looked at impact of goal amount on success ad fail, the impact of campaign length
on outcome,whether a month in a year has an impact on the outcome,etc in the exploratory data analysis..the results of which are summarized further in the PDF report.

Predictive Modeling -
Due to Kickstarter’s “All or Nothing” model, what forms the core of this analysis is the end result of a project –
success or failure. Keeping that goal in mind, we built a couple of predictive models to classify a project as a
success or failure based on certain attributes. In this case, we used the following attributes to determine the
end status of the project based on the relationships discovered between in the exploratory data analysis. The
following attributes were used as our independent variables in predictive modelling - ‘main category’,
‘category’, ‘launched month’, ‘deadline month’, ‘goal’, ‘duration ’ ; all that are set by the user on initiating a
project on Kickstarter.
Prior to implementing the classification techniques on our data, we encoded categorical variables such as
main category and sub category and divided our data into train and test using a 77-33 split. The classification
models that we implemented were - Logistic regression, Random forest and kNN.
Amongst the 3 models, we found Random Forest to be the most suitable fit for our data because of a relatively
higher accuracy rate and a higher area under the ROC curve. The Random Forest method (with 100
estimators) took comparatively less time to run than kNN.

#### Conclusion  
We have been able to leverage this data to gain insight into Kickstarter project outcomes and understand that there are many nuances to the outcome or the success of a project and it’s not just about size of a project or the general popularity of the domain under which it falls.
Some of the main and specific takeaways from our analysis are :

* Projects that achieve success generally have a duration of 32-38 days.
* Projects that have a goal set to < $ 50k have better chances of being funded and even being overfunded up to 5 times it’s goal.    
* Projects in the artistic space such as Dance, Music, Theatre have better odds of succeeding owing to the shorter duration and modest goals set.
* Projects in categories such as Tech, Design are harder to fund despite having a larger base of backers owing to high goals set for such projects. Having said this, such projects that have a modest goal will have an excellent chance to succeed, owing to these same characteristics. 

The data does have predictive power. Our model using random forecast classification yielded an accuracy rate of 63% in predicting the outcome of projects.

We would like to do the following to enhance our analysis and improve our accuracy in predicting the outcome of projects on Kickstarter-

* Source data that contains more attributes which can help predict better such as project origin city, social media tags, user history, project description which based on our research correlate strongly to project outcomes.
* Leveraging advanced feature engineering and techniques of classification.
* Robust validation in determining model performance.
* Handle outlier detection in a sophisticated way.
* Further functionality -> Predict the time that a project can take to achieve it’s goal. To also predict the number of backers a project would require to meet its funding requirement.

Our analysis would be useful to -
* People or Creators who want to check how their project or campaign can perform on Kickstarter before they invest time and efforts in launching it on the website. And to be able to accordingly adjust project specs and goal which could help the maximize their chances of success.
* People or Backers who want to determine the outcome of  project based on it’s current state before they commit to donating money.


