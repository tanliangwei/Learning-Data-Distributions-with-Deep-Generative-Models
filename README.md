# Learning Data Distributions with Deep Generative Models

In this repository, we test the ability of Deep Generative Models to learn the distributions of datasets. We got our models to learn and generate 2 different datasets. One is conducted on the New York City Taxi Trip Duration Dataset and the other one is the 2015 Flight Delays and Cancellation Dataset. The links are listed below.

[https://www.kaggle.com/c/nyc-taxi-trip-duration/data](https://www.kaggle.com/c/nyc-taxi-trip-duration/data)

[https://www.kaggle.com/usdot/flight-delays](https://www.kaggle.com/usdot/flight-delays)


## New York City Taxi Dataset Experiments

### Downloading Required Packages

Run the following command

```
pip3 install -r requirements.txt
```

### Preparing the Data

To prepare the data, we took out the columns `'pickup_longitude`, `pickup_latitude`, `dropoff_longitude`, `dropoff_latitude`, `passenger_count`, `trip_duration` from `train.csv` (the original data file downloaded from Kaggle) and save it in that order in a file named `processed_nyc_train.csv`. These files are not present in the repository.

### Deep Generative Models

There are 6 different sub-directories, each with one model.

1. NYC VAE - VAE Model
2. NYC VAE MDN - VAE with MDN
3. NYC MAF - 12 layers of MAF
4. NYC MAF BN - 12 layers of MAF with batch normalization
5. NYC RNVP 8 - 8 layers of RNVP with batch normalization
6. NYC RNVP 12 - 12 layers of RNVP with batch normalization

Each of it contains a jupyter notebook. To make the model learn about the data distribution and generate samples, run the cells in the notebook sequentially.

## 2015 Flight Delays and Cancellation Dataset Experiments

### Downloading Required Packages

Run the following command

```
pip3 install -r requirements.txt
```

### Preparing the data

The data is prepared inside the data sub-directory. There is a notebook, `data_process.ipynb` inside which can generated the dataset for experiments.  It will join the 2 spreadsheets `airports.csv` and `flights.csv` (Downloaded from the Kaggle link), take out the columns `origin_longitude`, `origin_latitude`, `destination_longitude`, `destination_latitude`, `depature_delay`, `arrival_delay` and save it in that order inside `processed_data.csv`. Before using `flights.csv` for the join, remove all columns except `ORIGIN_AIRPORT`, `DESTINATION_AIRPORT`,	`DEPARTURE_DELAY`, `ARRIVAL_DELAY`.

Note that `origin_longitude` and `origin_latitude` are the coordinates of the origin airport and `destination_longitude` and `destination_latitude` are coordinates of the destination airport.

### Deep Generative Models

There are 4 different sub-directories, each with one model.

1. FLIGHT MAF -  12 layers of MAF
2. FLIGHT MAF BN - 12 layers of MAF with batch normalization
3. FLIGHT RNVP 8 - 8 layer of RNVP with batch normalization
4. FLIGHT RNVP 12 - 12 layer of MAF with batch normalization

Each of it contains a jupyter notebook. To make the model learn about the data distribution and generate samples, run the cells in the notebook sequentially.
