# Overview 
![trck](https://user-images.githubusercontent.com/83923903/147840488-ea85014a-2948-4e77-a31b-80b451a3340e.jpeg)




**Scenario**: Chelsea B, CEO and co founder of **Air Freight Cargo Company** a global air freight forwarding logistics company based out of South san francisco with over 150 additional warehouses located around the world. "AFCC" large regional hubs handles trucks from logistical centers and their service is critical to getting product sorted and shipped. Chelsea has just contracted an external data analyst, Jack to perform some analysis. Chelsea's crm has done a great job, and stored a ton of helpful goods to customers. In the Data, we have information such as transaction id, the customer phone number, the spotID (gate number) they offloaded Cargo at, The date/time the customer arrived at the slot, and finally the amout of money they paid. However, like most datasets there exist dirty or even duplicated data which needs to be removed. This way we can ensure we made a through analysis. 

Chelsea goal is creating 3 metrics bring back to her Q4 meeting with her fellow stakeholders, in order drive the business forward by leveraging our historical data 

Chelsea has tasked Jack to help clean, explore, and disover new business implimentations. Jack has decided to break the Data analysis process down into two parts.


# Part 1: Data Clean up. Google Sheets, Pandas
# Part 2: KPI & Dashboard


## Part 1
Link to Original Dirty Data: https://docs.google.com/spreadsheets/d/1Dh4nBFfJPPOIJrTz4lU-0ZiHGWDLfXfSR_f1zvMhnJI/edit?usp=sharing
Link to Clean Data: https://docs.google.com/spreadsheets/d/18cKkNBf_Bi2-Gjcmiu8F-3LonrmKtFBPCMxJ9tMqOSg/edit?usp=sharing


#### Open Provided CSV. We immedietly notice errors in column "amount_paid_cents" with the number formated with a space "#_###". We need to remove the space in between and we will use the Substitute formula. This will remove the space inbetween the numbers and give us the correct format. Next we create a new column called "Amount Paid in Dollars" We will be use this column later. We notice additional errors in the "Zip Code" and decide to use Pandas to fix this. So, We save the CSV as AG_test.CSV and into our resource folder.

<img width="987" alt="Screen Shot 2021-12-29 at 11 21 55 PM" src="https://user-images.githubusercontent.com/83923903/147731600-fdc82021-e76b-4c31-a50f-ba9a1b0ee0ed.png">

#### First we upload our CSV into Juypter notebook and reformat into a dataframe with pandas. Next we split date & time from Created_at_UTC Column.

<img width="895" alt="Screen Shot 2021-12-30 at 12 58 27 PM" src="https://user-images.githubusercontent.com/83923903/147787596-48b68b09-7aa7-4ad7-8831-4962c8f641a7.png">


#### Next we should Clean all of the "Zip Code". We notice major errors in Zip code column and decide to use a sort value on the Zip codes. We then identified 28 rows of invalid Data, to be deleted. We only pull the remaning 472 rows from our Dataframe.

<img width="847" alt="Screen Shot 2021-12-29 at 11 35 51 PM" src="https://user-images.githubusercontent.com/83923903/147731926-2c68da86-aca6-4a45-8582-05b3d0049c2e.png">

#### we save our new Dataframe. We convert and save this Dataframe back into AG_test2.csv
<img width="917" alt="Screen Shot 2021-12-31 at 2 04 02 PM" src="https://user-images.githubusercontent.com/83923903/147839885-63ac5bad-57b7-4183-93bb-9c6107b240af.png">

#### With most of the error taken care of, we manually review the dataset and fix small errors.
Link to dataset: https://docs.google.com/spreadsheets/d/18cKkNBf_Bi2-Gjcmiu8F-3LonrmKtFBPCMxJ9tMqOSg/edit?usp=sharing


# Part 2: KPI & Dashboard
#### Questions to Ask: 
**Q** Chelsea: Where are all of these customers located around the world? Can we seperate them by wins and losses? **A** Jack: Lets create a GEO Map.
Blue = Wins
Orange = Losses
<img width="154" alt="Screen Shot 2021-12-31 at 2 29 25 PM" src="https://user-images.githubusercontent.com/83923903/147840302-0c1c30fe-785c-4402-860e-1ee11735bd52.png">

<img width="1134" alt="Screen Shot 2021-12-31 at 2 29 17 PM" src="https://user-images.githubusercontent.com/83923903/147840312-4973df16-80d9-46b8-9e5a-9832b9a263ed.png">



**Q** Jack :How much are we willing to pay, to acquire the customer? Chelsea: **A:** $50 is our Customer acquisition Cost.

Anytime a customer spends above $50 at a spot, we are in the Black. Anytime a customer pays below $50 for a spot we unfortunately are in the red. With the Average transaction at $51.29, we have a sweet spot of 1.29 (2.58%) margin to profit of each transation. Great! 

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

## KPI: Surge Rate & Upselling opportunitys: We notice upticks at specific times of the day. Some worth over $70 at times. We should impliment an additional 0.10 cent increase to these surge times. This will add to our revenue. As our margins are 1.29, an addiitonal 0.10 cents is a 7% increase in revenue. We can identifiy these surge trends from our historical data. 
**

<img width="1136" alt="Screen Shot 2021-12-31 at 2 25 46 PM" src="https://user-images.githubusercontent.com/83923903/147840252-2650b30f-b94b-4d10-b65b-6d00f524af58.png">


### Please use the fully interactive Dashboard Link Below: 
https://public.tableau.com/app/profile/jack.guo4626/viz/AGTest_16409597631390/Dashboard1?publish=yes


# Additional Comments & Road Blocks

* Some additional data like "Duration of Stay" so we could figure out when the spot was open again would be useful.
* There is only 1 phone number per row of data. If 1 phone number = 1 customer then, the dataset could be more variation as repeating customers are not being accounted for. 
* 

* PostgreSQL not compatable with Tableau Public. Limited to only using google sheets....
<img width="691" alt="Screen Shot 2021-12-31 at 11 47 55 AM" src="https://user-images.githubusercontent.com/83923903/147840405-6d654084-b72a-427c-b843-2687a65f5bcd.png">


* Unwilling to pay for a monthly license,($52) as my free two week trail was used during Berkeley Bootcamp

* Spent time Creating a postgreSQL server, was unable to use it. I creating tables in hopes to connect postgresql it with amazon S3 and connecting that to Tableau. But If i had a full version of Tableau Desktop, this is how I prefer to do it. Google sheets works, but not scalable and in my opinion serves as a band aid.
<img width="1418" alt="Screen Shot 2021-12-31 at 2 36 14 PM" src="https://user-images.githubusercontent.com/83923903/147840415-acd9e7f7-1000-4b6f-a776-3bfd9a0250f4.png">

