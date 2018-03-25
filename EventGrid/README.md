![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/EventGrid/images/eventgrid.jpg "Header Image")
# Capture Device Creation/Deletion using Event Grid and Send Email using Logic Apps

#### Azure IoT Hub integrates with Azure Event Grid so that you can send event notifications to other services and trigger downstream processes. Configure your business applications to listen for IoT Hub events so that you can react to critical events in a reliable, scalable, and secure manner. For example, build an application to perform multiple actions like updating a database, creating a ticket, and delivering an email notification every time a new IoT device is registered to your IoT hub


## Create Logic App

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/EventGrid/images/01_Create_Logic_App.png "Create Logic App")


![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/EventGrid/images/02_Create_LogicApp_Submit.png "Create Logic App")


## Using Logic App Designer, Create New App

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/EventGrid/images/03_Logic_App_designer.png "Create App")


![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/EventGrid/images/04_Http_Request.png "Select HTTP Request")


## Using Logic App Designer, Create New App

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/EventGrid/images/03_Logic_App_designer.png "Create App")


![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/EventGrid/images/04_Http_Request.png "Select HTTP Request")


![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/EventGrid/images/05_Sample_Payload.png "Provide Sample Payload")


```code
[{
  "id": "56afc886-767b-d359-d59e-0da7877166b2",
  "topic": "/SUBSCRIPTIONS/<Subscription ID>/RESOURCEGROUPS/<Resource group name>/PROVIDERS/MICROSOFT.DEVICES/IOTHUBS/<IoT hub name>",
  "subject": "devices/LogicAppTestDevice",
  "eventType": "Microsoft.Devices.DeviceCreated",
  "eventTime": "2018-01-02T19:17:44.4383997Z",
  "data": {
    "twin": {
      "deviceId": "LogicAppTestDevice",
      "etag": "AAAAAAAAAAE=",
      "status": "enabled",
      "statusUpdateTime": "0001-01-01T00:00:00",
      "connectionState": "Disconnected",
      "lastActivityTime": "0001-01-01T00:00:00",
      "cloudToDeviceMessageCount": 0,
      "authenticationType": "sas",
      "x509Thumbprint": {
        "primaryThumbprint": null,
        "secondaryThumbprint": null
      },
      "version": 2,
      "properties": {
        "desired": {
          "$metadata": {
            "$lastUpdated": "2018-01-02T19:17:44.4383997Z"
          },
          "$version": 1
        },
        "reported": {
          "$metadata": {
            "$lastUpdated": "2018-01-02T19:17:44.4383997Z"
          },
          "$version": 1
        }
      }
    },
    "hubName": "egtesthub1",
    "deviceId": "LogicAppTestDevice",
    "operationTimestamp": "2018-01-02T19:17:44.4383997Z",
    "opType": "DeviceCreated"
  },
  "dataVersion": "",
  "metadataVersion": "1"
}]
```


## Setup Notification by Sending Email 

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/EventGrid/images/06_New_Step.png "Notification Steps")

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/EventGrid/images/07_Add_new_Action.png "Notification Steps")

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/EventGrid/images/08_Choose_Mail.png "Notification Steps")

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/EventGrid/images/09_send_email.png "Notification Steps")

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/EventGrid/images/10_signin_to_email.png "Notification Steps")

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/EventGrid/images/11_Send_Email.png "Notification Steps")


## Copy Request URL

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/EventGrid/images/12_eventurl.png "Event URL")


## Integrate With IoTHub

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/EventGrid/images/13_IoTHub_EventHub.png "Integrated with IoTHub")

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/EventGrid/images/14_empty_event_subscription.png "Integrated with IoTHub")

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/EventGrid/images/15_device_events.png "Integrated with IoTHub")


## Add Device and Test Notification

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/EventGrid/images/16_add_device.png "Add Device")

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/EventGrid/images/17_add_device.png "Add Device")

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/EventGrid/images/18_email_generated.png "Email Notification")


## Delete Device and Test Notification

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/EventGrid/images/19_delete_device.png "Delete Device")

![Imported Script](https://github.com/rangv/AzureIoTLabs/blob/master/EventGrid/images/20_email_generated.png "Email Notification")
