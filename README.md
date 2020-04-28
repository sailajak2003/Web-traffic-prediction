
# Web Traffic Time Series Prediction

I used Time Series Analysis to predict web page views on Wikipedia. The idea is to run predictions at scale. 

Businesses need to get accurate forecasts of things like items to stock, pricing for ads, expected loads etc there is a growing need to predict better and for a lot of data. 

I used Facebook's Prophet model to predict future time series here along with Spark to parallelize the whole process so I can predict at scale.

Here is how i did this.
 
#### 1. Data Exploration
 
I am using Wikipedia page web traffic data from Kaggle.

This data has more than 465,000 rows and 550 columns. These represent the various wikipedia pages and the views for each page over time.

**Daily Seasonality**: I tried to check if there is any daily seasonaility in the model but i coud not find much daily seasonality.

**Yearly Seasonality**: I could certainly see a lot of pages having yearly seasonaility so I decided to use Yearly Seasonality for all the pages in my model.

           
#### 2. Feature Engineering 
 
The below are the some of the feature engineering steps

**Melting** 

**GroupBy Page** 

**UDF to call Prophet** 


#### 3. Modelling

As mentioned before I used Facebook's Prohpet model to run these predictions. The reason why I chose this model instead of stanard ARIMA or SARIMAX models is due to the simplicity and the accuracy of the model.

**Growth**: I tried to run various models with Growth Parameter set to both Linear and Logistic and i found its better to use the later.

**Cap**: Inspite of trying to predict the caps, i realized a no-cap input was tracking the actual pageviews better than setting artificial caps.

#### 4. Final Result
Here are a few images of how the model performed.

**Christmas Carol**
<img src="/images/Tableau_Christmas_Carol.png"  width="900" height="500">

**Abraham Lincoln**
<img src="/images/Tableau_Abraham_Lincoln.png"  width="900" height="500">

**Game of Thrones**
<img src="/images/Tableau_GOT.png"  width="900" height="500">

**Adidas**
<img src="/images/Tableau_Adidas.png"  width="900" height="500">





