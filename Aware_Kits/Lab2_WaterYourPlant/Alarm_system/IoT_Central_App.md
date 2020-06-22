# Creating a new IoT Central application template

You have already created an IoT Central Application in [Lab 1](../../Lab1_MonitoryourPlan/IoTCentral/Create_app_IoTCentral.md). For this scenario, you will need to add a new interface to your device template so that a command to trigger the alert system can be sent to the device.

## Create a new device template

As seen previously, device types are defined using templates - these specify the capabilities of the device including the telemetry that can be received from the device, and commands that can be sent to it.

We have already created a device template that receives temperature, humidity, air pressure, soil moisture and light conditions from your sensor device. You will need to define a new template that has these values on it, as well as a new command that communicates to the raspberry pi when the plant needs to be watered.

1. From the left panel select **Device Template**. Then click on **+ New**.

   ![device template](./media/device_template.png)

1. Select the **IoT Device** template.

   ![iot device](./media/create_device_template.png)

1. Select the **Next: Customize** button.

1. Select the **Next: Review** button.

1. Select the **Create** button.

1. Name the template `IrrigationMonitor`.

## Create the Capability Model

Once the template is created, you need to add capabilities to it as you have done previously. These are defined using **capability models**, which define the capabilities of all devices that will use this template. 

1. Select the **Custom** capability model

1. Click on **+Add interface**

   ![The add interface option](./media/add_interface.png)

1. Select **Custom** interface

   ![The custom interface option](./media/choose_interface.png)


1. Select the **+ Add capability** button to add new capabilities, and add the following values:

   |  Display Name     | Name          | Capability Type | Semantic Type | Schema | Unit |
   | -------------     | ------------- | --------------- | ------------- | ------ | ---- |
   | Temperature       | temperature   | Telemetry       | Temperature   | Double | °C   |
   | Pressure          | pressure      | Telemetry       | Pressure      | Double | kPa  |
   | Humidity (%)      | humidity      | Telemetry       | Humidity      | Double | %    |
   | Soil Moisture (%) | soil_moisture | Telemetry       | None          | Double | % |
   | Light Level (%)   | light_level   | Telemetry       | None          | Double | % |

1. Additionally, you will need to add a command to communicate to the device that the plant needs to be watered.

   |  Display Name     | Name             | Capability Type |
   | -------------     | -------------    | --------------- |
   | Needs Watering    | needs_watering   | Command         |

   [Add screenshot]


   Turn on Request for the command and set the following values:

   |  Display Name     | Name             | Schema |
   | -------------     | -------------    | --------------- |
   | Needs Watering    | needs_watering   | Boolean         |

   [Add screenshot]

## Add a view

1. Select **Views** from the menu.

   ![select view from pannel](./media/add_view.png)

1. Select Visualizing the device

   ![select new view](./media/select_new_view.png)

1. Set the view name to `Overview`. We will use this view to show the charts of the values recorded.

1. Configure the dashboard to your liking. As with the capabilities in the telemetry section, you will be able to drag *Needs Watering* from the *Commands* section onto the dashboard.

   [add screenshot]

1. Select the **Save** button from the top menu

   ![The save view button](./media/save_view.png)


   Here is an example of how it can look like.

   ![sensor charts](./media/chart_view.png)

   ![sensor data](./media/sensor_view.png)

## Publish the device template


1. Select the **Publish** button from the top-most menu.

   ![publish template](./media/publish_template.png)

1. Click on Publish.

   ![publish](./media/confirm_publish_device.png)

## Create a device

You will need to create a new device, and connect your device as you have done previously.

1. Go to **Devices** > **IrrigationMonitor**.

   ![devices](./media/devices_sensorMonitor.png)

1. Select **+ New**.

1. Set the **Device Name** to `Lab 2 Sensor` and the **Devide Id** to `raspberry_pi_2`. Then Click on **Create**.

   ![create device](./media/create_device.png)

A new device should appear in the devices list.

![device list](./media/device_list.png)

### Get the device connection details

Each device has a seet of connection details that will be used on the actual device to connect to Azure IoT Central and send telemetry.

1. Click on the Raspberry pi device you have just created.

1. Click on the `Connect` button located at the top right corner.

   ![connect device](./media/connect_device.png)

1. Take note of the **ID Scope**, **Device Id** and **Primary key**. You will need these values to send the data from the raspberry pi.

   ![connection details](./media/device_connection_details.png)

------------------

[Next Step](./Send_data_to_IoTCentral.md): write the python code to send telemetry data to IoT Central.
