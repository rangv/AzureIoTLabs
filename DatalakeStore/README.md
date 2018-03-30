![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/DatalakeStore/images/datalakestore.jpg "Header Image")
# Create Data Lake Store and Stream Data from IoTHub using Azure Stream Analytics

#### Azure Data Lake Store is an enterprise-wide hyper-scale repository for big data analytic workloads. Azure Data Lake enables you to capture data of any size, type, and ingestion speed in one single place for operational and exploratory analytics. Data Lake Store can store trillions of files. A single file can be larger than one petabyte in size. This makes Data Lake Store ideal for storing any type of data including massive datasets like high-resolution video, genomic and seismic datasets, medical data, and data from a wide variety of industries.


## Create Azure Data Lake Store

#### Create a hyper scale data lake store to store IoT Data. 

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/DatalakeStore/images/01_Create_Datalake_Store.png "Create Datalake Store")

#### 

#### During creation of data lake you have the choice to encrypt the store

#### Data Lake Store protects your data assets and extends your on-premises security and governance controls to the cloud. Your data is always encrypted, while in motion using SSL, and at rest using service or user-managed HSM-backed keys in Azure Key Vault. Single sign-on (SSO), multi-factor authentication, and seamless management of millions of identities is built-in through Azure Active Directory. Authorize users and groups with fine-grained POSIX-based ACLs for all data in your store and enable role-based access controls. Meet security and regulatory compliance needs by auditing every access or configuration change to the system.

#### 

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/DatalakeStore/images/02_Create_Datalake_Store_Submit.png "Create Datalake Store")

#### 

## Explore Data in Data Lake Store

#### 

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/DatalakeStore/images/03_Datalake_Store_Date_Explore.png "Explore Data")

#### 


## Create Folders in Data Lake Store

#### Create /workshop/streaming folder to store Streaming data coming from your device through IoTHub using Stream Analytics Job

#### 

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/DatalakeStore/images/04_Datalake_Store_Date_Explore_create_folder_workshop.png "Explore Data")

#### Create /workshop/streaming folder

#### 

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/DatalakeStore/images/05_Datalake_Store_Date_Explore_create_folder_workshop_streaming.png "Explore Data")

#### 

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/DatalakeStore/images/06_Datalake_Store_Date_Explore_created_folder.png "Explore Data")

#### 

## Create Stream Analytics Job

#### Azure Stream Analytics is a managed event-processing engine set up real-time analytic computations on streaming data. The data can come from devices, sensors, web sites, social media feeds, applications, infrastructure systems, and more

#### 

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/DatalakeStore/images/07_Create_Stream_Analytics_Job.png "Create Stream Analytics Job")

#### 

#### Stream Analytics job cab be created to run on the cloud as well as on the Edge. You will chose to run this on the cloud

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/DatalakeStore/images/08_Create_Stream_Analytics_Job_submit.png "Create Stream Analytics Job")

#### 

#### Add Input for Streaming Job, IotHub will be the input

#### 

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/DatalakeStore/images/09_Add_Input.png "Add Input")

#### 

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/DatalakeStore/images/10_Add_IoTHub.png "Add Input")

#### 

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/DatalakeStore/images/11_Save_IoTHub.png "Add Input")

#### 

## Add Output for Streaming Job, Data Lake Store will be the output

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/DatalakeStore/images/12_Add_Data_Lake_Store.png "Add Output")

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/DatalakeStore/images/13_Add_Output.png "Add Output")

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/DatalakeStore/images/14_Save_Output.png "Add Output")

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/DatalakeStore/images/15_Save_Output_2.png "Add Output")

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/DatalakeStore/images/16_Save_Output_3.png "Add Output")


## Edit Query for Streaming Job, Stream Data from IoTHub to Datalake Store

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/DatalakeStore/images/17_Edit_Query.png "Edit Query")


```sql
SELECT
    *, System.Timestamp as time
INTO
    DatalakeStore
FROM
    IotHub
```

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/DatalakeStore/images/18_Save_Query.png "Edit Query")

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/DatalakeStore/images/19_Save_Query_Yes.png "Save Query")




## Start Streaming Analytics Job

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/DatalakeStore/images/20_Start_Stream_Analytics_Job.png "Start Job")

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/DatalakeStore/images/21_Start_custom.png "Start Job")

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/DatalakeStore/images/22_running.png "Job running")


## Explore Streaming Data

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/DatalakeStore/images/23_datalake_store_explore_streaming_data.png "Explore Streaming Data")

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/DatalakeStore/images/24_datalake_file.png "Explore Streaming Data")
