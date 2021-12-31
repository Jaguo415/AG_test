# Overview 
![ramp](https://user-images.githubusercontent.com/83923903/147833790-2d88081c-beeb-4f06-b529-25a999a9ecec.jpeg)



**Scenario**: Chelsea B, CEO and co founder of **Air Freight Cargo Company** a global air freight forwarding logistics company based out of South san francisco with over 50 additional warehouses located around the world. "AFCC" handles large cargo trucks from logistical centers and their service is critical to getting product sorted and shipped. Chelsea has just contracted an external data analyst, Jack to perform some analysis. Chelsea's crm has done a great job, and stored a ton of helpful customer data. In the Data, we have information such as transaction id, the customer phone number, the spotID (gate number) they offloaded Cargo at, The date/time the customer arrived at the slot, and finally the amout of money they paid. However, like most datasets there exist dirty or even duplicated data which needs to be removed. This way we can ensure we made a through analysis. 

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

**Q**:How much are we willing to pay, to acquire the customer? **A:** $50 is our Customer acquisition Cost. 

Anytime a customer spends above $50 at a spot, we are in the Black. Anytime below $50 the red. With the Average transaction at $51.29, we have a sweet spot of 1.29 (2.58%) to profit. 

*** KPI: Customer acquisition cost  ($50)
<img width="488" alt="Screen Shot 2021-12-31 at 11 47 09 AM" src="https://user-images.githubusercontent.com/83923903/147839853-9734d053-879d-444d-9db5-6f83ba23b73e.png">

* KPI:              ( $ Profitable - # of profitable transactions * 50) = True Revenue
*                   ($ unprofitable - # of Unprofitable transactions * 50) = missed Revenue 
*                   True Revenue + missed Revenue = Gross Revenue

* 17,775 - 237 * 50 = 17,775 - 11,850 = $5905 True Revenue
* 5974 - 226 * 50 = 5,974 - 11,300 = -$5326 missed Revenue
* 5905 + (-5326) = $579 Gross profit 

* KPI: Surge Rate & Upselling opportunitys: We notice upticks at specific times of the day. We should impliment at 0.10 cent increase to add to our revenue. As our margins are 1.29, an addiitonal 0.10 cents is 7% increase in revenue identified from our historical data. 
**

### Dashboard Link: 
https://public.tableau.com/app/profile/jack.guo4626/viz/AGTest_16409597631390/Dashboard1?publish=yes

