---
platform: debian, Linux, raspbian, Ubuntu, windows
device: any
language: Python
---

Run a simple Python sample on device
===
---

# Table of Contents

-   [Introduction](#Introduction)
-   [Step 1: Prerequisites](#Prerequisites)
-   [Step 2: Prepare your Device](#PrepareDevice)
-   [Step 3: Run the Sample](#Run)

<a name="Introduction"></a>
# Introduction

**About this document**

This document describes how to run the **iothub_client_sample.py** Python sample application. This multi-step process includes:
-   Configuring Azure IoT Hub
-   Registering your IoT device
-   Build and deploy Azure IoT SDK on device

<a name="Prerequisites"></a>
# Step 1: Prerequisites

You should have the following items ready before beginning the process:
-   Computer with Git client installed and access to the
    [azure-iot-sdk-python](https://github.com/Azure/azure-iot-sdk-python) GitHub public repository.
-   [Prepare your development environment][lnk-python-devbox-setup]
-   [Setup your IoT hub][lnk-setup-iot-hub]
-   [Provision your device and get its credentials][lnk-manage-iot-hub]

<a name="PrepareDevice"></a>
# Step 2: Prepare your Device

-   Make sure desktop is ready as per instructions given on [Prepare your development environment][lnk-python-devbox-setup].

> Note: On Windows, you can install the **iothub-client** module package using Pip as described in [Prepare your development environment][lnk-python-devbox-setup].

<a name="Run"></a>
# Step 3: Run the sample

- Navigate to the folder **python/device/samples** in your local copy of the repository.

- Open the file **iothub_client_sample.py** in a text editor.

- Locate the following code in the file:

    ```
    connectionString = "[device connection string]"	
    ```

- Replace `[device connection string]` with the connection string for your device. Save the changes.

- Run the sample application using the following command:

    ```
	python iothub_client_sample.py
    ```

- The sample application will send messages to your IoT hub. The **iothub-explorer** utility will display the messages as your IoT hub receives them.

If you receive the error "ImportError: dynamic module does not define module export function (PyInit_iothub_client)" you may be running the samples with a different version of python than the iothub_client was build with. Following the [Prepare your development environment](#python-devbox-setup) to ensure the library is built with the desired python version

# Experimenting with various transport protocols
There is a command line switch to test each of the AMQP, HTTP and MQTT protocols. It is also possible to simply change the transport in the sample.

    ```
	python iothub_client_sample.py -p <mqtt|http|amqp>
    ```

# Debugging the samples (and/or your code)
[Visual Studio Code](https://code.visualstudio.com/) provides an excellent environment to write and debug Python code:
- [Python Tools for Visual Studio](https://www.visualstudio.com/en-us/features/python-vs.aspx)

<a name="NextSteps"></a>
# Next Steps

You have now learned how to run a sample application that collects sensor data and sends it to your IoT hub. To explore how to store, analyze and visualize the data from this application in Azure using a variety of different services, please click on the following lessons:

-   [Manage cloud device messaging with iothub-explorer]
-   [Save IoT Hub messages to Azure data storage]
-   [Use Power BI to visualize real-time sensor data from Azure IoT Hub]
-   [Use Azure Web Apps to visualize real-time sensor data from Azure IoT Hub]
-   [Weather forecast using the sensor data from your IoT hub in Azure Machine Learning]
-   [Remote monitoring and notifications with Logic Apps]   

[Manage cloud device messaging with iothub-explorer]: https://docs.microsoft.com/en-us/azure/iot-hub/iot-hub-explorer-cloud-device-messaging
[Save IoT Hub messages to Azure data storage]: https://docs.microsoft.com/en-us/azure/iot-hub/iot-hub-store-data-in-azure-table-storage
[Use Power BI to visualize real-time sensor data from Azure IoT Hub]: https://docs.microsoft.com/en-us/azure/iot-hub/iot-hub-live-data-visualization-in-power-bi
[Use Azure Web Apps to visualize real-time sensor data from Azure IoT Hub]: https://docs.microsoft.com/en-us/azure/iot-hub/iot-hub-live-data-visualization-in-web-apps
[Weather forecast using the sensor data from your IoT hub in Azure Machine Learning]: https://docs.microsoft.com/en-us/azure/iot-hub/iot-hub-weather-forecast-machine-learning
[Remote monitoring and notifications with Logic Apps]: https://docs.microsoft.com/en-us/azure/iot-hub/iot-hub-monitoring-notifications-with-azure-logic-apps
[lnk-setup-iot-hub]: ../setup_iothub.md
[lnk-manage-iot-hub]: ../manage_iot_hub.md
[lnk-python-devbox-setup]: python-devbox-setup.md
