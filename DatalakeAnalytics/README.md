![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/DatalakeAnalytics/images/datalakeanalytics.png "Header Image")
# Create Data Lake Analytics Service and run U-SQL jobs

#### Learn how to use Data Lake Analytics to run big data analysis jobs that scale to massive data sets. Tutorials and other documentation show you how to create and manage batch, real-time, and interactive analytics jobs, and how to query using the U-SQL language


## Create Azure Data Lake Analytics Service

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/DatalakeAnalytics/images/01_Create_Data_Lake_Analytics_Service.png "Create Datalake Analytics Service")

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/DatalakeAnalytics/images/02_Create_Data_Lake_Pick_Store.png "Pick A Store")

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/DatalakeAnalytics/images/03_Create_Data_Lake_Analytics_Success.png "Create Service")


## Create Sample Data

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/DatalakeAnalytics/images/04_Create_Data_Lake_Analytics_Sample_Scripts.png "Create Sample Data")

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/DatalakeAnalytics/images/05_Create_Data_Lake_Analytics_Sample_Data.png "Create Sample Data")

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/DatalakeAnalytics/images/06_Create_Data_Lake_Analytics_Sample_Data_Successful.png "Create Sample Data")


## Install Extenstion


![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/DatalakeAnalytics/images/07_Create_Data_Lake_Analytics_Install_Extensions.png "Install Extensions")

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/DatalakeAnalytics/images/08_Create_Data_Lake_Analytics_Install_Extensions_Success.png "Install Extensions")


## Submit Job using VS Code, Try Samples First to Learn through Data Lake Analytics

#### Install VS Code Extension for Data Lake Analytics
![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/DatalakeAnalytics/images/data-lake-tools-for-vscode-extensions.png "Install Extensions")

#### Run Samples

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/DatalakeAnalytics/images/09_VSCode_Open_Sample_Script.png "Run Samples")

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/DatalakeAnalytics/images/10_VSCode_Open_Sample_Script_Compile.png "Run Samples")

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/DatalakeAnalytics/images/11_VSCode_Open_Sample_Script_Compile_Select_Account.png "Run Samples")

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/DatalakeAnalytics/images/12_VSCode_Open_Sample_Script_Compile_Account.png "Run Samples")

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/DatalakeAnalytics/images/13_VSCode_Open_Sample_Script_Compile_master.png "Run Samples")

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/DatalakeAnalytics/images/14_VSCode_Open_Sample_Script_Compile_usql.png "Run Samples")

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/DatalakeAnalytics/images/15_VSCode_Open_Sample_Script_Compile_submit.png "Run Samples")

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/DatalakeAnalytics/images/16_VSCode_Open_Sample_Script_Submit_Job.png "Run Samples")


![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/DatalakeAnalytics/images/17_VSCode_Open_Sample_Script_Submit_Job_success.png "Run Samples")

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/DatalakeAnalytics/images/18_VSCode_Open_Sample_Script_Submit_Job_success_portal.png "Run Samples")

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/DatalakeAnalytics/images/19_VSCode_Open_Sample_Script_Input_Data.png "Run Samples")

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/DatalakeAnalytics/images/20_VSCode_Open_Sample_Script_Output_Data.png "Run Samples")



## Create an Analytics Job against MXChip Data to convert JSON to CSV using U-SQL and Data Lake Analytics

### Create a new mxchip_analytics.usql file in the project


```sql
REFERENCE ASSEMBLY [Newtonsoft.Json];
REFERENCE ASSEMBLY [Microsoft.Analytics.Samples.Formats]; 

//Extract the Json string using a default Text extractor. 

@json = 
    EXTRACT jsonString string FROM @"/workshop/streaming/2018/03/{*}/{*}.json" USING Extractors.Tsv(quoting:false);

//Use the JsonTuple function to get the Json Token of the string so it can be parsed later with Json .NET functions

@jsonify = SELECT Microsoft.Analytics.Samples.Formats.Json.JsonFunctions.JsonTuple(jsonString) AS rec FROM @json;

@columnized = SELECT 
            rec["deviceId"] AS deviceId,
            rec["temperature"] AS temperature,
            rec["humidity"] AS humidity,
            rec["time"] AS time
    FROM @jsonify;



//Output the file to a tool of your choice.

OUTPUT @columnized
TO @"/workshop/output/out.csv"
USING Outputters.Csv();

```

#### Register two assemblies Newtonsoft and Samples.formats. Download the dlls from /libs folder and register

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/DatalakeAnalytics/images/21_Register_Assembly_Command.png "U-SQL Analytics")

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/DatalakeAnalytics/images/22_Register_Sample_Formats.png "U-SQL Analytics")


### Submit Job

#### Submit Job to convert all JSON files to CSV files

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/DatalakeAnalytics/images/23_SubmitJob.png "U-SQL Analytics")

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/DatalakeAnalytics/images/24_Submitted_Jobs.png "U-SQL Analytics")
