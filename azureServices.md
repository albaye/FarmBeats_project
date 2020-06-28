# Azure Services

## Azure Event Hubs

[Azure Event Hubs](https://azure.microsoft.com/services/event-hubs/#features?WT.mc_id=agrohack-github-jabenn) allow you to take streaming data and connect it to other services, such as storing the data or using Azure Stream Analytics to analyze the data in real time. Azure IoT Central can be configured to stream data to an Azure Event Hubs instance.
Data ingested have to be in json format. (Use “json.dumps()” method in python to convert to json).

## Azure Blob Storage

[Azure Blob Storage](https://azure.microsoft.com/services/storage/blobs/?WT.mc_id=agrohack-github-jabenn) allows us to store blobs (objects) of unstructured data that can be easily access from other Azure Services. Azure Storage can also store files, tables and queues.

## Azure Table Storage

[Azure Table Storage](https://azure.microsoft.com/services/storage/tables/) allows you to store up to petabytes of structure data, and access them using a key-value approach. The combination of the *partitionkey* and the *rowkey* has to be unique for each of the elements in the table.

## Azure Stream Analytics.

[Azure Stream Analytics](https://azure.microsoft.com/services/stream-analytics/?WT.mc_id=agrohack-github-jabenn) provides real-time analytics on streams of data, allowing us to stream data from one service to another. We will use it to pass the data from Azure Event Hubs (stream input) to Azure Blob storage (stream output). For this, we will need to create a new query, and start the job from the overview menu.

Check data is being stored in the Blob storage by going into the “Storage Explorer (preview)”, select the container, and download the json file.

## Azure Functions

[Azure Functions](https://azure.microsoft.com/services/functions/) is an event driven serverless compute platform, essentially a way to define small blocks of code that are triggered by events such as a web request, data changes in storage or events being put onto an Azure Event Hub. They can be written in a multitude of different languages including C#, F#, Java, JavaScript and Python.

Azure Stream Analytics can call Azure Functions in response to streaming data, either individual messages or and aggregation (i.e. if moisture is lower than a threshold, then the plant needs watering).

## Azure IoT Hub

[IoT hub](https://azure.microsoft.com/services/iot-hub/) is a platform made for IoT devices that makes communication between devices easier. Unlike Event hubs, which only allows one way communiction, IoT Hub allows us to have a bidirectional communication with enhaced security.

## Azure Maps

[Azure Maps](https://azure.microsoft.com/en-us/services/azure-maps/) is an Azure service that provides mapping and related data. You can use it for visualizing maps on a web page with added data, or requesting spatial data, such as if a coordinate is inside a shape on a map, and even weather data. It uses Geospatial APIs to add maps, spatial analytics, and mobility solutions to your apps.
