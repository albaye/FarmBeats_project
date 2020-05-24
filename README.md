# FarmBeats_project

## Official documentation
- [AgroHack](https://github.com/jimbobbennett/AgroHack)
- [FarmBeats Repo](https://github.com/farmbeatslabs/studentkit)
- [Example Repo using Azure Sphere]( https://github.com/gloveboxes/Azure-Sphere-Learning-Path)
- [Azure Tools: Microsoft Azure support for VS Code](https://marketplace.visualstudio.com/items?itemName=ms-vscode.vscode-node-azure-pack)


## Things to do
- How to send data from the AgroHack code that uses FarmBeats student kit hardware to the solution accelerator via the Event Hub (Event Hub can receive and send messages, whereas IoT Hub can receive). Document this process setup and ideally develop a scenario for this.

- Connect FarmBeats to IoT central dashboard to see data. (For the Aware kit just install Windows IoT core in the sd card and it ill send data automatically. For own raspberry pi use code in agrohack. We also need to add the data for the light sensor)
- Connect the kits or pi to Azure FarmBeats.
	- [Ingest Historical telemetry data in azure.](https://docs.microsoft.com/en-us/azure/industry/agriculture/ingest-historical-telemetry-data-in-azure-farmbeats)

	- [Telemetry Data Queries.](https://docs.microsoft.com/en-us/azure/industry/agriculture/query-telemetry-data-from-azure-farmbeats)
- Data export from Azure FarmBeats. (use Event Hubs and Stream Analytics to do this.)
- Develop app in PowerApps.

## Additional Info
This is from an [example using PowerApps and Azure Services](https://azure.microsoft.com/en-us/resources/videos/ignite-2018-creating-iot-solutions-with-microsoft-azure-and-powerapps/) ([Link to repo](https://github.com/OGcanviz/IoTPowerApp)). The fuctions are written in C#, but we can use python or javascript instead. [More Info](https://docs.microsoft.com/en-us/azure/azure-functions/supported-languages)

![Architecture](./images/Architecture_Example.png)

A resource group is like a project where all the specific tools from azure are stored for that specific project.	
![Resource Group](./images/ResourceGroup_Example.png)

App service contains all the functions used to get the data from IoT Hub and update data in the Hub from the App. The custom connector is from PowerApps. It calls the Function app from Azure. 


## Additional Comments

I think lab 0 should be the instructions of how to set up the kits (both aware and own raspberry pi). For the own raspberry pi, we would need to write python script to send data to the IoT Central app. The template is given, but we need to make the connection between the pi and the IoT app.

We should add some background information about why we think this scenario is relevant.

The files in the Scenarios folder will be the first document inside each lab to give and overview. Then start the practicals.
