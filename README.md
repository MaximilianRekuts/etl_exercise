The exercise:

Sold house prices:
Objective: Import data into local system and create queries to obtain some reports for our clients.
1. The first step would be to import the sold house price database (the data is here:
http://data.gov.uk/dataset/land-registry-monthly-price-paid-data, please use “FULL Price
Paid Data-Single file 1995-2017” CSV.)
a. The Table that we want to import this data is composed by: 
PRICE, TRANSFER_DATE, POSTCODE, TYPE, TOWN
b. The data should be checked before importing
i. Postcode should not be null
ii. Property type must be transformed: D -> DETACHED, S -> SEMI_DETACHED,
T -> TERRACED, F -> FLATS, O -> OTHER


2. After the import, we should create two reports for our clients:
a. the first report requires average prices for the given postcode and between the
given from and to dates, separated by flats, terraced homes, detached homes and
semi-detached homes. Dates should be aggregated. An example output could be
something like:
type;date;avg_price;
DETACHED;2005-01:90000
DETACHED;2005-02:100000
TERRACED;2005-01:95000

b. The second report shows the number of transactions at various price brackets given
a postcode and a year. Note that price brackets will be different in different
postcodes and date ranges so we should find a way to automatically generate the
price brackets. However, we can keep the number of brackets constant, to say 8.
Feel free to use either SQL or SQL + postprocessing in Python to do this.
An example output:
0-100000;2
100001-200000;10
200001-400000;100
