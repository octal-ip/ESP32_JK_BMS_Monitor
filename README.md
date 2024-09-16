# ESP32_JK_BMS_Monitor
A very simple customisation of the [esphome-jk-bms](https://github.com/syssi/esphome-jk-bms) project that provides MQTT and an external balancer output.

To build, [install ESPHome](https://esphome.io/guides/installing_esphome.html), then create your secrets.yaml file as below:

    wifi_ssid: (Your SSID)
    wifi_password: (Your Wi-Fi Password)
    mqtt_host: (Your MQTT host IP)
    mqtt_username: (Your MQTT username)
    mqtt_password: (Your MQTT password)
    mqtt_topic: (Your MQTT Topic)

Update the mac_address field in the main .yaml file with the BLE MAC of your BMS. This can be found using a BLE scanner tool such as bluetoothctl.

Connect the ESP32 to your computer via USB, then build and run the project:

    esphome run esp32-ble-jk02.yaml
    or
    esphome run esp32c3-ble-jk02.yaml


### Notes
- Two yaml files are provided - one for the original ESP32, and another for the ESP32-C3. I recommend using the ESP32-C3 Super Mini board as they're small, relable and very cheap.
- A relay for enabling an external active balancer can be connected to GPIO16 on the ESP32, or GPIO10 on the ESP32-C3.
- As BLE is used for connectivity to the BMS, there are no other inputs or outputs required.
- Further details on bulding and customising the esphome-jk-bms project are available on [syssi's GitHub page](https://github.com/syssi/esphome-jk-bms). Full credit goes to Sebastian Muszynski for his excellent work on the core of this piece of work.
