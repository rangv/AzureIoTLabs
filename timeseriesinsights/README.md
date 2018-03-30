![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/timeseriesinsights/images/timeseriesinsights.jpg "Header Image")
# Create Time Series Insights and Visualize Device Data

####

#### Learn how to set up a Time Series Insights environment, explore, and analyze time series data of your IoT solutions or connected things

####

## Create Time Series Insights

####

#### Azure Time Series Insights is a fully managed analytics, storage, and visualization service for managing IoT-scale time-series data in the cloud. It provides massively scalable time-series data storage and enables you to explore and analyze billions of events streaming in from all over the world in seconds. Use Time Series Insights to store and manage terabytes of time-series data, explore and visualize billions of events simultaneously, conduct root-cause analysis, and to compare multiple sites and assets. 

####

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/timeseriesinsights/images/01_Create_Time_Series_Insights.png "Create Time Series Insights")

####

#### Select the resource group you previously created and click Create button

####

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/timeseriesinsights/images/02_Create_Time_Series_Inisghts_Submit.png "Create Time Series Insights")


## Create Event Source

####

#### Create Event Source to connect to IoTHub. Please make sure you use a unique Consumer Group. Time Series Insights has a requirement to have its own unique consumer group

####

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/timeseriesinsights/images/03_Create_Event_Source.png "Create Event Source")

####

#### Select the appropriate consumer group and click Create button

####

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/timeseriesinsights/images/04_Create_Event_Source_Submit.png "Create Event Source")


## Visualize Data

####

#### Go To Time Series Insights, Click on Go To Environment which will take you to Time Series Insights Explorer

####

#### If you get Data Access Policy Error execute the following steps

####

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/timeseriesinsights/images/16_data_access_poliy_error.png "Data Access Policy Error")

####

#### Go To Environment Topology and 

####

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/timeseriesinsights/images/15_data_access_policy.png "Select Data Access Policy")

####

#### Click on Add Button

####

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/timeseriesinsights/images/17_add_user_role.png "Add User and Role")

####

#### Select Contributor Role

####

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/timeseriesinsights/images/18_select_controbutor_role.png "Select Contributor Role")

####

#### Select User

####

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/timeseriesinsights/images/19_select_user.png "Select User")

####

### Time Series Insights Explorer

####

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/timeseriesinsights/images/06_Visual1.png "Visualize Data")

####

### Go To Time Series Insights Explorer

####

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/timeseriesinsights/images/05_GoTo_TSI_Explorer.png "Visualize Data")

####

### Select Temperature and Split By ID

####

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/timeseriesinsights/images/07_Visual2.png "Visualize Data")

####

### Right Click to Explore events

####

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/timeseriesinsights/images/08_Visual3.png "Visualize Data")

####

### Explore Events in Tabular format

####

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/timeseriesinsights/images/09_Visual09.png "Visualize Data")

####

### Create a perspective with various charts

####

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/timeseriesinsights/images/10_visual10.png "Visualize Data")

####

### Select Humidity and ID

####

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/timeseriesinsights/images/11_visual11.png "Visualize Data")

####

### Create a chart by selecting a timeframe with drag feature

####

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/timeseriesinsights/images/12_Visual12.png "Visualize Data")

####

### Create 3rd Chart by adding a predicate

####

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/timeseriesinsights/images/13_Visual13.png "Visualize Data")

####

### Perspective with 4 different charts

####

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/timeseriesinsights/images/14_Visual_dashboard.png "Visualize Data")
