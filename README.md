# Project_C-Dac
This is the fornt-end portion of fraud detection system in which the user can check wheter their credit card transaction is fruadulent or not.


The needs the enter their transaction number and the rest of the details required in the form to check for fraud.


This check is performed by crosschecking the transaction number againt the database(balanced.csv) file and returning boolean value.


These are the steps to setup the project:-


Download Postgre and match the credentials to the ones in server.js file.


Create a table in postgres database by the name transactions using the following query :-

CREATE TABLE transactions (
    trans_date_trans_time TIMESTAMP,
    cc_num BIGINT,
    merchant VARCHAR(255),
    category VARCHAR(100),
    amt NUMERIC(10, 2),
    gender CHAR(1),
    street VARCHAR(255),
    city VARCHAR(100),
    state VARCHAR(2),
    zip VARCHAR(10),
    lat DECIMAL(10, 8),
    long DECIMAL(11, 8),
    city_pop INTEGER,
    job VARCHAR(100),
    trans_num VARCHAR(50),
    unix_time BIGINT,
    merch_lat DECIMAL(10, 8),
    merch_long DECIMAL(11, 8),
    is_fraud BOOLEAN
);

This the command to import the data form balanced.csv file into the transaction database:- 

COPY transactions (trans_date_trans_time, cc_num, merchant, category, amt, gender, street, city, state, zip, lat, long, city_pop, job, trans_num, unix_time, merch_lat, merch_long, is_fraud)
FROM '/path/to/your/file.csv' 
WITH (FORMAT csv, HEADER, DELIMITER ',');


The file also contains an analysis of the balanced.cdv file and various ml algorithms tested against the data to get the best predicition algorithm.
