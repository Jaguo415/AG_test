# Overview 


# Part 1: Data Clean up. Google Sheets, Pandas
# Part 2: SQL database set up
# Part 3: Tableau Dashboard and KPI


## Part 1

Facts: 
There is messy Data thats needs to be deleted as it does not add any benefit and as a by product will only add more confusion to our analysis.

1 Customer equals 1 uninque phone number. If same phone number in different Slot, still same customer.

Date and Time needs to be seperated into their own columns




#### Open Provided CSV. We immedietly notice errors in column "amount_paid_cents" with the number formated with a space "#_###". We need to remove the space in between and we will use the Substitute formula. This will remove the space inbetween the numbers and give us the correct format. Next we create a new column called "Amount Paid in Dollars" We will be use this column later. We notice additional errors in the "Zip Code" and decide to use Pandas to fix this. So, We save the CSV as AG_test.CSV and into our resource folder.

<img width="987" alt="Screen Shot 2021-12-29 at 11 21 55 PM" src="https://user-images.githubusercontent.com/83923903/147731600-fdc82021-e76b-4c31-a50f-ba9a1b0ee0ed.png">


#### Next we will use Pandas to Clean "Zip Code". We upload our CSV, and reformat it into a Dataframe. We notice most of the errors are in the Zip code column and decide to use a sort value on the Zip codes. We then identified 28 rows of invalid Data. We only pull the remaning 472 rows from our Dataframe, and we save our new Dataframe with 472/500 rows. We save this new Dataframe back into AG_test2.csv

<img width="847" alt="Screen Shot 2021-12-29 at 11 35 51 PM" src="https://user-images.githubusercontent.com/83923903/147731926-2c68da86-aca6-4a45-8582-05b3d0049c2e.png">

#### Seperate Date and Time into their own seperate columns. Use a Right and Left formula on Datetime column in google sheets.

<img width="969" alt="Screen Shot 2021-12-30 at 10 46 36 AM" src="https://user-images.githubusercontent.com/83923903/147780043-ebc3813d-226f-4bf0-9d02-78ca42123c37.png">

<img width="847" alt="Screen Shot 2021-12-30 at 10 46 11 AM" src="https://user-images.githubusercontent.com/83923903/147779959-7aab9b81-c8f1-4669-8956-0a3e08992497.png">




