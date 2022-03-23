# Content Based Filtering Movie Recommendations

## **Abstract**

## **Content**
1. Configure API
2. Extracting data
3. Preprocessing
4. Testing model
5. Extracting cover

## **1. Configure API**

### **Create account on website**
To extract data from website you need an api key. Go to [The Movie Data DB](https://www.themoviedb.org/) website and create an account:

![Create account](/images/create_account.png)

Fill the fields requested:

![Fill fields](/images/fill_data.png)

### **Get Api key**
Once you create an account, go to account settings, and select API tab in the left column, then you will see the api key (v3 auth).

![API key](/images/api_key.png)

### **API documentation**
See documentation in website [The Movie Data DB](https://www.themoviedb.org/documentation/api).

## **2. Extracting data from website**

To see how we retrieve data from website, check [ETL Jupyter Notebook](/etl_process.ipynb) step by step, attributes selected and how handle None values.

## **3. Preprocessing data**

Preprocessing data before put into model is important, we see how to do that in [ML Model Jupyter Notebook](/ml_model.ipynb).

## **4. Model creation and testing**

This information can also be found in [ML Model Jupyter Notebook](/ml_model.ipynb).

## **5. Extracting Top 10 covers**

Once we create the model, and getting top 10 movies recommendation we can retrieve the covers of this images and you will get something like this:

![Top ten image test](/images/top10.png)

This information can also be found in [ML Model Jupyter Notebook](/ml_model.ipynb).