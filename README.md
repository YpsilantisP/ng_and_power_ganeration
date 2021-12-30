# Project Plan
<br>
<br>

## Project Goal
#### __<font color='salmon'> Project Aim and Objectives</font>__
1. Fetching, transforming, cleaning, saving the data locally and allowing the user to updated them in the future.
    * <font color='salmon'>OBJECTIVE 1 - Data Analysis:</font>
        1. connecting and fetching the data from the APIs
            * Carbon Intensity API returns JSON format data -- transforming them into tabular data (DataFrame) is required before saving locally.
            * The data from Yahoo are fetched as a DataFrame; therefore,  no actions are needed.
        2. Data cleansing, Investigating for null values and possible errors.
        3. Storing the datasets locally to be reusable, avoiding fetching repeatedly from the APIs.
        4. Enable the user to update the local dataset -- prompting them to use same script in the future.
<br>

2. Using statistical tools to understand the datasets.
    * <font color='salmon'>OBJECTIVE 2 - Data Visualisation (including descriptive statistics):</font>
        1. Analysing their properties using min, max, mean etc.  
        2. Understanding the distributions of the fuels
        3. Finding correlations between the fuels.
        4. Finding their trends throughout seasonality.
<br>

3. Predicting future moves of gas commodity stock using the first dataset (independent variable) machine learning tools.
    * <font color='salmon'>OBJECTIVE 3 - ML pipeline (Predicting gas movements):</font>
        1. Creating graphs for gas stock prices dataset to gain information and understand it.
        2. Merging the two datasets to prepare for the ML model.
        3. Standardising and separating the dataset into test and train.
        4. Fitting the new data into an SVR model to produce predictions.


<br>
<br>

## Data

#### __<font color='salmon'>This project includes two datasets</font>__.
1. The percentage of fuels used for electricity generation in the GB __(Carbon Intensity API)__
2. Gas stock prices __(Yahoo)__.

#### __<font color='salmon'>Columns</font>__


#### _Fuels used for electricity (Carbon Intensity API)_


| Dates | biomass | coal | imports | imports  | nuclear | other | hydro | solar | wind |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 2019-03-31 23:30:00| 9.9 | 0.0 | 10.0 | 28.9 | 26.1 | 0.3 | 1.3 | 0.0 | 23.5 |


#### _Gas stock prices (Yahoo Finance API)_

| Dates | High | Low | Open | Close | Volume | Adj. Close |
| --- | --- | --- | --- | --- | --- | --- |
| 2019-01-04 | 3.049 | 2.894 | 2.914 | 3.044 | 122576.0 | 3.044 |

#### __<font color='salmon'>Description of the Datasets:</font>__

The Carbon Intensity API includes half-hourly data (in our case from 01/01/2019 up to October 01/01/2021), describing the percentage of fuels used for<br>
electricity generation.

Yahoo finance includes the natural gas stock prices from the stock market of NY. This dataset has daily records that describe the movements of the gas as a <br>
commodity -- using as a unit of measurement, USD dollars.


#### __<font color='salmon'>Data limitations & validity:</font>__

The first problem was the lack of data for gas from the London exchange market which will have a more direct relationship. However, all these<br>
big markets are connected -- revealing co-movements on their commodities. Especially for the USA which one of the most important importers of UK's<br>
natural gas (see link 5) we could assume that a connection of supply and demand could affect the commodity. So it was worth investigating, as energy<br>
is a hot topic.

The second problem in these data was the inconsistency between them. The first dataset is half-hourly, while the second one is daily and<br>
they have different units of measurement. Also, because of its nature (stock market prices), the second dataset lacks of data during weekends.

Finally, for the validity of these sources; Carbon Intensity API is one of the most trustworthy APIs in the energy sector for the GB,<br>
developed from National Grid ESO, Environmental Defense Fund Europe, University of Oxford (cs department) and WWF. Yahoo finance has always<br>
been one of the most valuable tools for getting accurate information for the stock market -- well know for its accuracy.

#### __<font color='salmon'>Links:</font>__
1. https://carbonintensity.org.uk/
2. https://carbon-intensity.github.io/api-definitions/
3. https://finance.yahoo.com/quote/NG%3DF/
4. https://pypi.org/project/fix-yahoo-finance/0.1.30/
5. [Natural gas imports for UK](https://assets.publishing.service.gov.uk/government/uploads/system/uploads/attachment_data/file/1006628/DUKES_2021_Chapter_4_Natural_gas.pdf)

<br>
<br>

## System Design

#### __<font color='salmon'> Architecture</font>__


* The first section (Program Code) includes all the code used for the analysis.<br>
* The second section (Project Outcome) includes the interpretation of the results.<br>
* The third section (Conclusions) summarises the outcome and future work.<br>

<br>
<br>

## To install 
* Install project requirements
    * pip install -r requirements.txt
