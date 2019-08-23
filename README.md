# data-generation-projection
This is the solution for a task which requires generation of data according to requirements with a use of provided DataGenerator class, further preprocessing of this data and simulation of data projections for analysis of it.

## Provided requirements for the data:
1. There should be up to 12 records with the same full_name while the other data can be different. A particular number of such records should be uniformly distributed
2. The user-defined random number seed should be used to generate the same data again if you define the same seed. 
3. Data should be saved into a CSV file: 
InputData_YYYYMM_SEED_YYYYMMDDHHMMSS.csv, 
here YYYYMM - valuation_date (e.g. 2020/01), 
SEED - random number generator seed (see #2),
YYYYMMDDHHMMSS - timestamp of the moment when the file was published on the file system
4. The number of records is not limited but should be statistically representative

## For data preprocessing and validation further requirements were provided:
A Numpy array of records should be created:

1. user_id - integer number (primary key, an identity of the user)
2. gender - integer number
3. expiration_date - integer year, integer month and integer day (end-of-month). Should be present as special numpy dtype
3. loan - floating point number array with a size 10 (number of payment programs)

Some separate tables will be useful too:
1. Mapping of the user_name to user_id (or backward)
2. Mapping of gender real name to its integer representation
3. Assuming we have 10 payment programs we can create a mapping of their ids to their names (e.g. P0, P2 etc. or any other unique names)

