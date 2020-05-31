# Create Event Hubs

## Step 1: Create Event Hubs
Azure Event Hub service allows us to manage millions of events. In this case we will use it to export the data from the IoT Central App.

### Create from Portal
1. Log into your azure portal.

1. Click on **Create a Resource**.

1. Search for Event Hubs and select `Event Hubs`.

1. Click on **Create**.

1. Fill in the detials for the storage account.

   1. Select your Azure subscription.

   1. Create a new resource group. 

   1. Choose a namespace for the Event hub. In this case, we chose farmbeats data.

   1. Choose your location.

   1. Select Basic Pricing Tier.

1. Click on Review + Create.

1. Click on Create.

1. Once the deployment has finished, press on go to resource.


## Step 2: Setting up the Storage Account
### Create Storage Account
1. Log into your azure portal.

1. Click on **Create a Resource**.

1. Search for storage account and select `Storage account - blob, file, table, queue`.

1. Click on **Create**.

1. Fill the details of the Storage account. 

   1. Select your Azure subscription.

   1. Select the Resource Group created above.

   1. Give the storage acount a name. In this case we chose farmbeatsdata.

   1. Select your location.

   1. Set the replication to be Locally-redundant Storage (LRS).

   1. Leave the rest as it is.

1. Click on **Review + Create**.

1. Select **Create**.

1. When the deployment is finished, click on Go to resource button. 

### Create a container
1. Go to Containers in the left panel.

1. Click on `+ Container`.

1. Name the container **sensorData**.

This will allow us to store the data received from the Sensors.

## Step 3: Stream Analytics Job.
Stream Analytics Job takes and input, in our case it will be an event hub, and send results to an output after doing some processing if needed.

### Create Stream Analytics Job.
1. Log into your azure portal.

1. Click on **Create a Resource**.

1. Search for stream analytics and select `Stream Analytics Job`.

1. Click on **Create**.

1. Fill the details of the Stream Analytics Job. 

   1. Name the job `TelemetryStreaming`.
   
   1. Select your Azure subscription.

   1. Select the Resource Group created above.

   1. Select your location.

   1. Leave the rest as it is.

1. Click on **Review + Create**.

1. Select **Create**.

1. When the deployment is finished, click on Go to resource button. 

### Configure the Azure Stream Analytics Job

#### Set an input 
1. Under Job Topology in the left panel, click on **Inputs**.

1. Select `+ Add stream input`, then select **Event Hub**.

1. Fill in the input details.

   1. Set the alias to be telemetry.

   1. Select `Select Event Hub from your subscriptions`.

   1. Select your subscription and Azure Event hubs Namespace.

   1. Select `Use Existing` for the **Event Hub Namespace**.

   1. Select the event hub created earlier.

   1. Leave the rest of the options as the defaults.

   1. Click on **Save**. 

#### Set an output
1. Under Job Topology in the left panel, click on **Outputs**.

1. Select `+ Add stream output`, then select **Blob storage/Data Lake Storage**.

1. Fill in the output details.

   1. Set the alias to be *blob storage*.

   1. Select `Select storage from your subscriptions`.

   1. Select your subscription and Storage Account.

   1. Select `Use Existing` for the **Container**.

   1. Select the container created earlier.

   1. Set the *Path* to `{date}/{time}`. JSON records are appended to a single JSON file, and setting this will cause a new file to be created each hour in a folder hierarchy based off *year/month/day/hour*.

   1. Leave the rest of the options as the defaults.

   1. Click on **Save**. 

#### Create query
1. Under Job Topology in the left panel, click on **Query**.

1. Change the query to be the following:
    ```sql
    SELECT
        *
    INTO
        [blob-storage]
    FROM
        [telemetry]
    ```
1. Select **Test Query** to test the query and see a sample output using real data from tha event hub.

1. Select **Save Query**.

#### Start the job
1. In the left panel, go to the **Overview** tab.

1. Select **Start**.

1. For the *Job ouput start time* select **Now**.

1. Select **Start**.

## Step 4: Create App

