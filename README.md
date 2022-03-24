# Content Based Filtering Movie Recommendations

## **Description**

This project makes a list recommendation of 10 movies based on watched movie.

The project is composed of two jupyter notebooks, the first part is call [etl_process.ipynb](/etl_process.ipynb) and this show how to retrieve information using the movie db API, transform data to select attributes we will use in our model, and finally load processed data to [dataset_movies.csv](/dataset_movies.csv) and removing None data.

The second part is in [ml_model.ipynb](/ml_model.ipynb), here we will show how to process data generated in first part to be suitable for recommendation model and test model with different distance metrics.

## **Content**

```
1. Configure API
2. Extracting data
3. Preprocessing
4. Model creation an testing
```

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

To see how we retrieve data from website, check [ETL Jupyter Notebook](/etl_process.ipynb) here are the instructions to get data movies step by step.

1. Retrieve data using requests library
2. Load data as dictionary using json library
3. Processing dictionary removing unnecesary attributes
4. Binarize genre attribute
5. Getting dataset of all movies id [movie_ids_03_16_2022.json](/movie_ids_03_16_2022.json)
6. Retrieve data and processing iterative for all movies id and append to [dataset_movies.csv](/dataset_movies.csv)
7. Removing duplicates, fill None dates with 0 for release_date and runtime
8. Update final [dataset_movies.csv](/dataset_movies.csv)
9. Create a table of count movies by genre and export to [genres_counts.csv](/genres_counts.csv)

### **DataFrame (dataset_movies.csv)**

![DataFrame final processing](/images/dataframe_final.jpg)

## **3. Preprocessing data**

Preprocessing data before put into model is important, some preprocessing is:

1. Droping rows with dates before 1900, cause some problems in excel and we are not interest on very old movies.
2. Eliminate title movies from model (we don't use by now)
3. Change from dates to ordinal data.
4. Replace None dates with mean ordinal dates.
5. Normalize data using MinMaxScaler just for non binary data (first 7 columns)

### **DataFrame input data model**

![Data frame after preprocessing.](/images/processed_data.JPG)

This information can be found in [ML Model Jupyter Notebook](/ml_model.ipynb).

## **4. Model creation and testing**

Model consist on 10 nearest neighbors using distance metrics (euclidean distance).

Model example: "Batman: Gotham Knight"

![Batman: Gotham Knight](/images/example_image.jpg)

### **List prediction**

![Top 10 list](/images/top10list.jpg)

This information can also be found in [ML Model Jupyter Notebook](/ml_model.ipynb).

### **Extracting Top 10 covers**

Once we create the model, and getting top 10 movies recommendation we can retrieve the covers of this images and you will get something like this:

![Top ten image test](/images/top10.png)

This information can also be found in [ML Model Jupyter Notebook](/ml_model.ipynb).