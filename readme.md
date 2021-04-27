# Mobile Open Observation of Daily Stressors (MOODS)

The purpose of the MOODS study is to understand what causes stress in daily life (i.e., daily stressors), focusing on those stress events that can be detected by wearable wrist sensors.

## MD2K
The Center of Excellence for Mobile Sensor Data-to-Knowledge (MD2K), headquartered at University of Memphis, was established via a grant (#U54EB020404) from the National Institutes of Health (NIH) in 2014 to develop novel computing technologies to use mobile sensor data for improving health and wellness.

# Data Summary

This data is from the MOODS study conducted at the University of Memphis.  There are 60,000 participant annotated episodes (stress or non-stress).  Participants participated for 100 study days and could provide up to 6 annotated episodes per day.  

## Participant Privacy
Participant identifiers have been removed and all episodes assigned a global identifier.  Absolute timing has been removed to further preserve this privacy.  Instead, we provide both the day of the week and time of the day for all data points.

## Metadata
The included metadata documents (.json) fully describe the data and its meaning.


## Data Structure
The sensor data is stored within sensor specific folders and numbers according to the associated episode (e.g. `data/accelerometer/5467.parquet`, `data/gyroscope/5467.parquet`, `data/ppg/5467.parquet`) all contain the data associated with episode 5467 in the `data/episode.parquet` file.  This episode file contains a table of all the episodes and associated metadata as described in the `episode.json` file.


# Processing Data
These data files are setup to be read by either Pandas  

```
import pandas as pd
episodes = pd.read_parquet('data/episodes.parquet')
accelerometer = pd.read_parquet('data/accelerometer/5467.parquet') # Note, you need to read in each episode as you process them.
```

or Apache Spark

```
episodes = spark.read.parquet('data/episodes.parquet')
accelerometer = spark.read.parquet('data/accelerometer') # Note, can read the whole data set when run.
```
