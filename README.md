# Azure IOT 
This repo contains working examples for Azure IOT communication.
Prerequesite: Azure Connection String
Hardware Used: Toradex Colibri iMX8X, Toradex Colibri Evaluation Board
Enable IOT extension in Azure CLI: `az extension add --name azure-cli-iot-ext `

## 1. Receive Act React
Issue the following command from Azure CLI to send message to the Colibri. Upon right message, LEDs in Colibri Eval. Board starts Blinking:
Right message: `az iot device c2d-message send --device-id colibri-imx8x --hub-name Toradex-test-hub --data "Start"`
Wrong message: `az iot device c2d-message send --device-id colibri-imx8x --hub-name Toradex-test-hub --data "Hey There!"`

## 2. Web Apps Node IOT Hub
This repo that captures the "LED State" sent from the device to the cloud, and visualizes in a WebApp

1. Receive a message
2. If right message act by blinking LED
3. Report the LED State back to the Azure cloud

Debug Command (Cross check the recieved messages in Azure CLI)
`az iot hub monitor-events --hub-name Toradex-test-hub --output table`
