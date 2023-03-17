# ESP32_JK_BMS_Monitor
A very simple customisation of the [esphome-jk-bms](https://github.com/syssi/esphome-jk-bms) project that provides MQTT and an external balancer output.

To build, [install ESPHome](https://esphome.io/guides/installing_esphome.html), then create your secrets.yaml file as below:

    wifi_ssid: (Your SSID)
    wifi_password: (Your Wi-Fi Password)
    mqtt_host: (Your MQTT host IP)
    mqtt_username: (Your MQTT username)
    mqtt_password: (Your MQTT password)
    mqtt_topic: (Your MQTT Topic)

Update the mac_address field in esp32-ble-jk02.yaml with the MAC of your BMS.

Connect your ESP32 via USB, then build and run the project:

    esphome run esp32-ble-jk02.yaml


### Notes
- A relay for enabling an external active balancer can be connected to GPIO16.
- Any ESP32 dev board that exposes GPIO16 is suitable for this project. As BLE is used for connectivity to the BMS, there are no other inputs or outputs required. The Wemos D1 mini32 is the selected board in the YAML file.
