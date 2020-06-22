## Set up an alarm system

#### **Objective**

Set up a system to alert the user when the plant needs to be watered.

#### **Learning outcomes**

- Investigate creating rules using Azure IoT Central
  - Send email or push notification when the soil moisture is below a certain threshold.

  - Optional: check if temperature/pressure/light intensity is outside the optimal range.

  - Learn to use Azure Events Hub, Azure Stream Analytics and Azure Functions to process data.
  - Determine the date and time that the plant was last watered.

#### **Key areas to teach**

IoT Azure Services, Data, Microcontroller Programming, AI.

_Optionally a LED indicator can be integrated to indicate if the plant needs watering._


#### **Steps:**

1. [Set up your hardware](Setup_hardware.md)
1. [Create a new device template for IoT Central App](IoT_Central_App.md)
1. [Create a rule in IoT Central](IoT_Central_create_rule.md)
1. [Create an Azure Function](Create_Azure_Function.md)
1. [Execute IoT Command](Execute_IoT_Command.md)
1. [Write code for the alarm system](AlarmSystem.md) 