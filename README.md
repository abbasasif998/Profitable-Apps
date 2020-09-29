# Project on Profitable App Profiles for the Apple Store and Google Play Markets.
## Aim
Our aim in this project is to find mobile app profiles that are profitable for the App Store and Google Play markets. We're hypothetically working as data analysts for a company that builds Android and iOS mobile apps, and our job is to enable our team of developers to make data-driven decisions with respect to the kind of apps they build.
At our company, we only build apps that are free to download and install, and our main source of revenue consists of in-app ads. This means that our revenue for any given app is mostly influenced by the number of users that use our app. Our goal for this project is to analyze data to help our developers understand what kinds of apps are likely to attract more users.

## Collecting Data 
As of September 2018, there were approximately 2 million iOS apps available on the App Store, and 2.1 million Android apps on Google Play.

Collecting data for over four million apps requires a significant amount of time and money, so we'll try to analyze a sample of data instead. To avoid spending resources with collecting new data ourselves, we should first try to see whether we can find any relevant existing data at no cost. Luckily, these are two data sets that seem suitable for our purpose:

* [A data set](https://www.kaggle.com/lava18/google-play-store-apps) containing data about approximately ten thousand Android apps from Google Play. You can download the data set directly from [this link](https://dq-content.s3.amazonaws.com/350/googleplaystore.csv).
* [A data set](https://www.kaggle.com/ramamet4/app-store-apple-data-set-10k-apps) containing data about approximately seven thousand iOS apps from the App Store. You can download the data set directly from [this link](https://dq-content.s3.amazonaws.com/350/AppleStore.csv).

## Opening and Exploring Data
Opening both .csv using open() command and reading it. For easily exploring the dataset we defined a function explore_data that printed components of each row and leaving a gap line between two rows.

## Cleaning and Preprocessing Data
* On exploring the data we found there were some rows with wrong information so we deleted the row with wrong data entry.
* Some apps were repeated in the Google Play Store Dataset whereas IOS AppStore Dataset was free of this duplicacy of Data. To tackle this we used the Data which was recent (meaning which had the maximum number of reviews).
* Our company primarily focuses on free apps. But both the Dataset contained Paid Apps also. So extracted the Data of all the free apps from both the Dataset.
* There were some Non-English apps also keeping in mind our company specifically targets english speaking audience. We applied Algorithms to extract of all the apps which had a English Name. 

## Transforming and Analysing Data
### Most Common Apps by Genre
#### Part One
As we mentioned in the introduction, our aim is to determine the kinds of apps that are likely to attract more users because our revenue is highly influenced by the number of people using our apps.

To minimize risks and overhead, our validation strategy for an app idea is comprised of three steps:

Build a minimal Android version of the app, and add it to Google Play.
If the app has a good response from users, we then develop it further.
If the app is profitable after six months, we also build an iOS version of the app and add it to the App Store.
Because our end goal is to add the app on both the App Store and Google Play, we need to find app profiles that are successful on both markets. For instance, a profile that might work well for both markets might be a productivity app that makes use of gamification.

Let's begin the analysis by getting a sense of the most common genres for each market. For this, we'll build a frequency table for the prime_genre column of the App Store data set, and the Genres and Category columns of the Google Play data set.

Part Two
We'll build two functions we can use to analyze the frequency tables:

One function to generate frequency tables that show percentages
Another function that we can use to display the percentages in a descending order
