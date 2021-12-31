# Overview 
![ramp](https://user-images.githubusercontent.com/83923903/147833790-2d88081c-beeb-4f06-b529-25a999a9ecec.jpeg)



**Scenario**: Chelsea B, CEO and co founder of **Air Freight Cargo Company** a freight forwarding warehouse based out of South san francisco with over 50 additional warehouses located around the world. "AFCC" handles large cargo trucks from logistical centers and their service is critical to getting product sorted and shipped. Chelsea has just contracted an external data analyst, Jack to perform some analysis. Chelsea crm has done a great job, its stored a ton of helpful data. In the Data, we have information such as transaction id, the customer phone number, the spotID (gate number) they offloaded Cargo at, The date/time the customer arrived at the slot, and finally the amout of money they paid. However, like most CRM theres dirty or duplicated data which needs to be removed.

Chelsea goal is creating 3 metrics bring back to her Q4 meeting with her shareholders, in order push the business forward by using our historical data Chelsea has tasked Jack to help better drive business decisions. Jack has decided to break the process down into two parts.


# Part 1: Data Clean up. Google Sheets, Pandas
# Part 2: Tableau Dashboard and KPI


## Part 1
Link to Original Dirty Data: https://docs.google.com/spreadsheets/d/1Dh4nBFfJPPOIJrTz4lU-0ZiHGWDLfXfSR_f1zvMhnJI/edit?usp=sharing
Link to Clean Data: https://docs.google.com/spreadsheets/d/18cKkNBf_Bi2-Gjcmiu8F-3LonrmKtFBPCMxJ9tMqOSg/edit?usp=sharing


#### Open Provided CSV. We immedietly notice errors in column "amount_paid_cents" with the number formated with a space "#_###". We need to remove the space in between and we will use the Substitute formula. This will remove the space inbetween the numbers and give us the correct format. Next we create a new column called "Amount Paid in Dollars" We will be use this column later. We notice additional errors in the "Zip Code" and decide to use Pandas to fix this. So, We save the CSV as AG_test.CSV and into our resource folder.

<img width="987" alt="Screen Shot 2021-12-29 at 11 21 55 PM" src="https://user-images.githubusercontent.com/83923903/147731600-fdc82021-e76b-4c31-a50f-ba9a1b0ee0ed.png">

#### First we upload our CSV into Juypter notebook and reformat into a dataframe with pandas. Next we split date & time from Created_at_UTC Column.

<img width="895" alt="Screen Shot 2021-12-30 at 12 58 27 PM" src="https://user-images.githubusercontent.com/83923903/147787596-48b68b09-7aa7-4ad7-8831-4962c8f641a7.png">


#### Next we should Clean all of the "Zip Code". We notice major errors in Zip code column and decide to use a sort value on the Zip codes. We then identified 28 rows of invalid Data, to be deleted. We only pull the remaning 472 rows from our Dataframe, and we save our new Dataframe with 472/500 rows. We save this new Dataframe back into AG_test2.csv

<img width="847" alt="Screen Shot 2021-12-29 at 11 35 51 PM" src="https://user-images.githubusercontent.com/83923903/147731926-2c68da86-aca6-4a45-8582-05b3d0049c2e.png">


# Part 2: Tableau Dashboard and KPI

#### Questions to Ask: 

Q:How much are we willing to pay, to acquire the customer? A: $50 is our Customer acquisition Cost

KPI: Customer acquisition cost ($50)
KPI: Net Revenue (Profitable / # of profitable transactions - unprofitable / # of Unprofitable transactions) 
KPI: Surge Rate & Upsell



