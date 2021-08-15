# Gov-Property-Data
Converting CSV to JSON, assigned unique IDs to every property. Unique IDs become index, independent variables are nested further. 



The government have made some datasets available, regarding property purchases which include the status of properties, their location and value. The datasets can be found in the following location
https://www.gov.uk/government/statistical-data-sets/price-paid-data-downloads

I have used the following dataset: http://prod.publicdata.landregistry.gov.uk.s3-website-eu-west-1.amazonaws.com/pp-complete.csv
In the code, I import it from my local area which I previously downloaded from the address above. 

The dataset itself does not have any column headers provided but the column descriptions can be found in the following location:
#https://www.gov.uk/guidance/about-the-price-paid-data#explanations-of-column-headers-in-the-ppd

As the data is imported in, the dataset will be required to be labelled. A list of column headers will be used as parameters for this. 

Looking through the data, there are some columns which are unncessary such as the transactionIDs, for the purpose of this task, and so will be removed. 


Once the basic data is loaded in, it's required to rearrange the data based on the properties and provide a unique ID to each property. To this end, each property must be unique. 

To create a unique address, the Secondary Address (such as flat number) is combined with the Primary Address (Street number) and Street Name. The postcode is also added on as this is still not yet unique. 

Now that we have the unique address, a unique ID can be applied. A basic approach was taken on this where all addresses are grouped and given a sequential ID. 


The data is now in order so now begins the process of exporting the data into a JSON file. The JSON file will have a single object per property, and an array within which shows the variables that change with time.

The property ID, and address are constant and as such are on a higher level. The variables such as date, price, tenure change with time and as such are nested further. 

The JSON file is then exported to a local area. 

