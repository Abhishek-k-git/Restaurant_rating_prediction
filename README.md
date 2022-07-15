![restaurant-prediction](https://github.com/Abhishek-k-git/Image/blob/main/Screenshot%20(7).png)

# Restaurant rating prediction 
#### Bangaluru restorant rating prediction in flask

![GitHub release (latest by date including pre-releases)](https://img.shields.io/github/v/release/navendu-pottekkat/awesome-readme?include_prereleases)
![GitHub last commit](https://img.shields.io/github/last-commit/navendu-pottekkat/awesome-readme)
![GitHub issues](https://img.shields.io/github/issues-raw/navendu-pottekkat/awesome-readme)
![GitHub pull requests](https://img.shields.io/github/issues-pr/navendu-pottekkat/awesome-readme)
![GitHub](https://img.shields.io/github/license/navendu-pottekkat/awesome-readme)

**Problem statement:**

> The basic idea of analyzing the Zomato dataset is to get a fair idea about the factors affecting the aggregate rating of each restaurant, establishment of different types of restaurant at different places, Bengaluru being one such city has more than 12,000 restaurants with restaurants serving dishes from all over the world. With each day new restaurants opening the industry has'nt been saturated yet and the demand is increasing day by day. Inspite of increasing demand it however has become difficult for new restaurants to compete with established restaurants. Most of them serving the same food. Bengaluru being an IT capital of India. Most of the people here are dependent mainly on the restaurant food as they don't have time to cook for themselves. With such an overwhelming demand of restaurants it has therefore become important to study the demography of a location. What kind of a food is more popular in a locality. Do the entire locality loves vegetarian food. If yes then is that locality populated by a particular sect of people for eg. Jain, Marwaris, Gujaratis who are mostly vegetarian. These kind of analysis can be done using the data, by studying different factors.


**From all the Data available, we can bring out some neat insights or conclusions such as**

- Which franchise has the highest number of Restaurants?
- How many Restaurants are accepting online orders?
- How many have a book table facility?
- Which location has the highest number of Restaurants?
- How many types of Restaurant types are there?
- What is the most liked Restaurant type?
- What is the Average cost for 2 persons?
- What is the most liked Dish type?


![dataset](https://github.com/Abhishek-k-git/Restaurant_rating_prediction/blob/master/table.png)


**Implemented Algorithms:**
- ExtraTreesRegressor


We know that data is messy. A dataset may contain multiple missing values. In that situation, we have to clean the dataset. To avoid this kind of hassle we are going to use a pre-cleaned dataset. You can download the dataset (.CSV file) from [here](https://archive.ics.uci.edu/ml/datasets/banknote+authentication)

``` pd.read_csv('data.csv') ``` - convert to pandas dataframe

``` data.isna().sum() ``` - check wheather this dataset contains any empty/null value or

**Data visualization:**

After dataprocessing or cleaning, it is very crucial to visualize dataset, there are many datavisualization tool out there. But here we use [seaborn](https://seaborn.pydata.org/), which is a python data visualization library based on matplotlib. It provides a high-level interface for drawing attractive and informative statistical graphics.

![map](https://github.com/Abhishek-k-git/Restaurant_rating_prediction/blob/master/map.png)

> **Training / Testing data split:**

Now data is divided into two sets one is *training dataset* which is used to train the model (just like a new born child learns by sensing things around him), the other dataset is *testing dataset* which is used to evaluate or predict the accuracy of model. The machine uses its model, apply to testing dataset to give out predicted results. The predicted output then compared to final result in actual dataset (In this case it is labeled as *class*). That's why it is necessary to first drop that column named class, before we train our model.

```
X = data.drop('class', axis = 1)
y = data['class']

# from sklearn.model_selection import train_test_split
x_train, x_test, y_train, y_test = train_test_split(X, y, test_size = 0.20, random_state = 1)
```
```
from sklearn.ensemble import ExtraTreesRegressor
```
```
reg = ExtraTreesRegressor(n_estimators=100, random_state=0);
reg.fit(X_train, y_train);
```





You can click here to take a [preview of app](https://restaurant-rating-prediction.herokuapp.com/)
