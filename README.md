# Overview 
![trck](https://user-images.githubusercontent.com/83923903/147840488-ea85014a-2948-4e77-a31b-80b451a3340e.jpeg)


## Our Scenario
Chelsea B, is the CEO and co founder of **Air Freight Cargo Company** a brand new global air freight forwarding logistics company based out of South san francisco with additional warehouses located around the world. "AFCC" has multiple regional hubs to handle inbound trucks from logistical centers. AFCC service is critical to getting product sorted and shipped on time thus customer success is very important. Chelsea has just contracted an external data analyst, Jack G to perform a in depth analysis. Chelsea's CRM has done a great job, at capturing and stored a ton of data. In the Data, we have information such as transaction id, the customer phone number, the spotID (gate number) they offloaded Cargo at, The date/time the customer arrived at the slot, and finally the amout of money they paid. However, like most datasets there exist dirty or even duplicated data which needs to be removed. This way we can ensure we made a through analysis. 

Chelsea goal is creating 3 metrics bring back to her Q4 meeting with her fellow stakeholders, in order drive the business forward by leveraging our historical data 

Chelsea has tasked Jack to help clean, explore, and disover new business implimentations. Jack has decided to break the Data analysis process down into two parts. 
# Resource: 
* Link to Dashboard
* https://public.tableau.com/app/profile/jack.guo4626/viz/AGTest_16409597631390/Dashboard1?publish=yes
* Link to Original Dirty Data: https://docs.google.com/spreadsheets/d/1Dh4nBFfJPPOIJrTz4lU-0ZiHGWDLfXfSR_f1zvMhnJI/edit?usp=sharing
* Link to Clean Data: https://docs.google.com/spreadsheets/d/18cKkNBf_Bi2-Gjcmiu8F-3LonrmKtFBPCMxJ9tMqOSg/edit?usp=sharing
* Challange.Ipynb python file


### Part 1: Data Clean up. Google Sheets, Pandas
### Part 2: KPI & Dashboard


## Part 1


#### Open Chelsea's Provided CSV. We immedietly notice errors in column "amount_paid_cents" with the number formated with a space "#_###". We need to remove the space in between and we will use the Substitute formula. This will remove the space inbetween the numbers and give us the correct format. Next we create a new column called "amount_paid_in_dollar". We take amount_paid_in_cents and multiply by one hundred. In order to get "amount_paid_in_dollar". We will be use this column later in our dashboard. We notice additional errors in the "Zip Code" and decide to use Python to fix this. So, We save the CSV as AG_test.CSV and into our resource folder.

<img width="772" alt="Screen Shot 2021-12-31 at 3 08 23 PM" src="https://user-images.githubusercontent.com/83923903/147840838-b05c8b14-d1a0-44a2-820a-78b4178db718.png">

<img width="753" alt="Screen Shot 2021-12-31 at 3 09 36 PM" src="https://user-images.githubusercontent.com/83923903/147840858-184fc8d6-e302-4579-9e98-e2ed218f646c.png">


#### First we upload our CSV into Juypter notebook and reformat the csv file into a dataframe with pandas a Python library. Next we split date & time from Created_at_UTC Column. Giving us two unique columns "Date", and "Time".

<img width="895" alt="Screen Shot 2021-12-30 at 12 58 27 PM" src="https://user-images.githubusercontent.com/83923903/147787596-48b68b09-7aa7-4ad7-8831-4962c8f641a7.png">


#### Next we should Clean all of the "Zip Code". We notice major errors in Zip code column and decide to use a sort value on the Zip codes. We then identified 28 rows of invalid Data, to be deleted. We only pull the remaning 472 rows from our Dataframe.

<img width="847" alt="Screen Shot 2021-12-29 at 11 35 51 PM" src="https://user-images.githubusercontent.com/83923903/147731926-2c68da86-aca6-4a45-8582-05b3d0049c2e.png">

#### we save our new Dataframe. We convert and save this Dataframe back into AG_test2.csv
<img width="917" alt="Screen Shot 2021-12-31 at 2 04 02 PM" src="https://user-images.githubusercontent.com/83923903/147839885-63ac5bad-57b7-4183-93bb-9c6107b240af.png">

#### With most of the error taken care of, we manually review the dataset and fix small errors.
Link to dataset: https://docs.google.com/spreadsheets/d/18cKkNBf_Bi2-Gjcmiu8F-3LonrmKtFBPCMxJ9tMqOSg/edit?usp=sharing


# Part 2: KPI & Dashboard


# Please use the fully interactive Dashboard Link Below: 
https://public.tableau.com/app/profile/jack.guo4626/viz/AGTest_16409597631390/Dashboard1?publish=yes

#### Questions to Ask: 
**Q** Chelsea: Where are all of these customers located around the world? Can we seperate them by wins and losses? **A** Jack: Lets create a GEO Map.
Blue = Wins
Orange = Losses
<img width="154" alt="Screen Shot 2021-12-31 at 2 29 25 PM" src="https://user-images.githubusercontent.com/83923903/147840302-0c1c30fe-785c-4402-860e-1ee11735bd52.png">
* Please note, you can only select 1 Region at a time. We have AMER View, but theres additiona views like european regions, Russia, Asia, Ect in the dataset. In addition You can switch your region on the bottom right of the GEO Map. 
<img width="1134" alt="Screen Shot 2021-12-31 at 2 29 17 PM" src="https://user-images.githubusercontent.com/83923903/147840312-4973df16-80d9-46b8-9e5a-9832b9a263ed.png">

**Q** Chelsea: How is each slot performing per quarter? Can we see the profitable vs unprofitable accounts?

<img width="1146" alt="Screen Shot 2022-01-28 at 8 40 24 AM" src="https://user-images.githubusercontent.com/83923903/151586587-b7370d73-50c5-47d9-9648-f95461180859.png">

**Q** Chelsea: What about each invidual slots performance? Can we break this down too for analysis?


<img width="1142" alt="Screen Shot 2022-01-28 at 8 40 36 AM" src="https://user-images.githubusercontent.com/83923903/151586807-dd0e8087-40c3-4708-9e0a-18d6692e345c.png">

**Q** Jack :How much are we willing to pay, to acquire the customer? Chelsea: **A:** $50 is our Customer acquisition Cost.

# Anytime a customer spends above $50 at a spot, we are in the Black. Anytime a customer pays below $50 for a spot we unfortunately are in the red. With the Average transaction at $51.29, we have a sweet spot of 1.29 (2.58%) margin to profit of each transation. Great! 

 ## KPI: Customer acquisition cost Formula
Profitable vs Unprofitable
<img width="488" alt="Screen Shot 2021-12-31 at 11 47 09 AM" src="https://user-images.githubusercontent.com/83923903/147839853-9734d053-879d-444d-9db5-6f83ba23b73e.png">

## KPI:
* Math:              ( $ Profitable - # of profitable transactions * 50) = True Revenue
*                   ($ unprofitable - # of Unprofitable transactions * 50) = missed Revenue 
*                   True Revenue + missed Revenue = Gross Revenue

* 17,775 - 237 * 50 = 17,775 - 11,850 = $5905 True Revenue
* 5974 - 226 * 50 = 5,974 - 11,300 = -$5326 missed Revenue
* 5905 + (-5326) = $579 Gross profit 

<img width="1147" alt="Screen Shot 2021-12-31 at 2 24 33 PM" src="https://user-images.githubusercontent.com/83923903/147840239-c533f132-2a6c-4ea0-bc67-40c0a0e6639b.png">

 ### Conclusion: We have made a profit of $579 As well as acquired 463 customers. This is great news for our shareholders! 

## KPI: Surge Rate & Upselling opportunitys: We notice upticks at specific times of the day. Any transaction over $50 is good. Sometimes the transactions worth over $60. We should impliment an additional 0.10 cent increase to these surge times. This will add to our revenue. As our margins are 1.29, an additonal 0.10 cents is a fantastic 7% increase in revenue. We can easily identifiy these surge times directly from our historical data. 
**


<img width="1139" alt="Screen Shot 2022-01-28 at 9 19 52 AM" src="https://user-images.githubusercontent.com/83923903/151592618-6f2221de-f817-4b3a-981b-779381ab1f5f.png">


# Additional Comments & Road Blocks

* Comment: Some additional data like "Duration of Stay" so we could figure out when the spot has "free time" knowing when spots are open again would be useful. So we can figure out white areas, and fill it with new customers. 
* Comment: There is only 1 phone number per row of data. If 1 phone number = 1 customer then, the dataset does not take into account of repeating customers.

* Roadblock: PostgreSQL not compatable with Tableau Public. Due Limited to only using google sheets.... Full Version of Tableau allows for SQL server connections.
<img width="691" alt="Screen Shot 2021-12-31 at 11 47 55 AM" src="https://user-images.githubusercontent.com/83923903/147840405-6d654084-b72a-427c-b843-2687a65f5bcd.png">


* Comment: Spent time Creating a postgreSQL server, but was unable to use it. I creating tables in hopes to connect postgresql it with amazon S3 and connecting that to Tableau. But If i had a full version of Tableau Desktop, this is how I prefer to do it. Google sheets works in this case because we only less than 500 rows of data. But using G sheets is not scalable and in my opinion serves as a band aid. We should get our dataset into SQL asap.

<img width="1418" alt="Screen Shot 2021-12-31 at 2 36 14 PM" src="https://user-images.githubusercontent.com/83923903/147840415-acd9e7f7-1000-4b6f-a776-3bfd9a0250f4.png">




