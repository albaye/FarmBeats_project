# Setting up your hardware

Before starting with this set of labs, you will need to check that your hardware is set up as suggested.

## Preparation

- Complete the steps to [assemble your hardware](../../Lab0_SetUp/1b_Assemble_your_FarmBeats_Student_Kit_Hardware.md) according to the guide in Lab0_Setup  

- Verify that the Capacitive Soil Moisture Sensor is plugged into socket A2 of the Grove Base Hat

- Verify that the Temperature, Humidity and Barometer Sensor (BME280) is plugged into the bottom left I2C socket of the Grove Base Hat.

![finished assembly](media/HardwareSetup.png)

## Optional LED Setup

For this lab, you have the option to set up an LED to light up when your soil moisture is below the optimal level for your plant.

If you wish to do this, you will need the [Grove - Red LED](https://wiki.seeedstudio.com/Grove-Red_LED/) module. Connect the Grove - Red LED module to port D2 of the Grove Base.

![Grove Red LED](media/GroveLEDRed.jpg)


## Additional Notes

You will not need the light sensor for this scenario, you may disconnect it from your sensor device if you wish.

----

#### **Previous instructions for reference:**

Mainly three sensors are used in this scenario. They are the Grove temperature and humidity sensor (GHT11), the Grove moisture sensor and the Grove red led.

Let's set up the **GHT11 sensor** first.

- Plug the Grove Base Hat into Raspberry Pi.

- Connect the temperature and humidity sensor to Port 12 of the Base Hat.

![Image](https://github.com/albaye/FarmBeats_project/blob/master/images/temphumid.jpg)

Similar instrustrustions are applied to the **moisture sensor** as well.

- Connect the Grove - Moisture Sensor to the A0 port of the Base Hat as sho

![Image](https://github.com/albaye/FarmBeats_project/blob/master/images/moisture.jpg)

Following is the instruction for **red led**.

- Connect Grove-Red LED to port D2 of Grove-Base Shield.

- After plugging in all the sensors above, connect the Raspberry Pi to PC through USB cable.

