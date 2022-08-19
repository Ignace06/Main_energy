PART I : Situation
Context :
Global warming is a long-lasting phenomenon and current scientific knowledge indicates that the increase in temperature is correlated with the emission of C02

Scope : 
Countries with high enough GDP and no missing values
Year : 2000-2018
Global energy consumption : electricity + transport + heating
Energies Unit : equivalent TWH

Problem statement:
What are the main primary energy sources that release C02 into the atmosphere?
What are the main continent/country responsable of C02 emission?

Main takeaway :
Coal is the main source of C02, followed by oil and both can explain 80% of the increase in C02 emissions
Asia (China in top) is by far the main responsable
There will be no global decline in C02 emissions in near future



PART II : Data sources & Data Frame
Origine :
Hannah Ritchie and Max Roser (2021) – Energy. Published in Our World in Data. Online at: ourworldindata.org/energy

Rows :
152 countries + years (1900-2020)
32 aggregated territories (useless, poorly filled) : USSR, East Africa, Low-income, …

Columns:
128 measures 
Input :
Population, GDP 
Added : GDP per capita / C02 per capita / C02 per GDP
Source of primary energies : Fossil energy // Renewable + Nuclear
Output
Million tons of CO2 equivalent



PART III : Data cleaning
To do to use clean data before data Viz + linear Model
- Round Value
- Change GDP in B$ + rename					(input)
- Change Pop in million + rename				(input)
- Rename greenhouse_gas_emissions : Million Tons  C02 eq	(output)
- Drop row from 1900-2000 + 2019-2021 : too many missing data	(input)
- Drop columns : keep only the consumption per energy source	(input)
- Drop Columns where population missing
- Drop gdp<100 000 000 000
- Drop useless agregate of countries with missing values
- Add columns Continent						(input)
- Add GDP/hab							(input)
- Add C02/hab							(input)
- Add C02/GDP							(input)



PART IV : Details steps
Import libraries
Exploring the database
Drop the unrelevant columns
Rename & Create relevant new columns for further analysis (C02 per cap, ...)
Check, fill or drop the missing value per country and per columns
Extraction dataframe for data Viz on Tableau
Selecting columns&rows, check correlation, train, split and run Linear model
Drop redundant rows : Asia is the sum of all asian countries and run heatmap matrix
Distribution plots of numerical variables
Selection minimum relevant columns for analysis : only consumption of each energy
Heatmap to check correlation, (output : 'M_Tons_C02_eq')
Train/test/split data
Apply the linear model & results



PART V : Results Linear Models
Result model with split in  70/30
R2 score of trained dataset is 0.988
R2 score of test dataset is 0.988
Mean absolute percentage error of train dataset is 2.59
Mean absolute percentage error of test dataset is 1.68


Which source of energy are responsible of C02 emission?
[('coal_consumption', 2442.0),
 ('oil_consumption', 1201.0),
 ('solar_consumption', 343.0),
 ('wind_consumption', 215.0),
 ('gas_consumption', 208.0),
 ('other_renewable_consumption', -9.0)]








