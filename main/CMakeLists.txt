#The IDF main component must be in the folder named 'main' unless you change the name through advanced settings.
idf_component_register(SRCS
                         "../main.cpp"
                       INCLUDE_DIRS
                         "."
                       PRIV_REQUIRES
                         esp_wifi
                         esp_timer
                         esp_netif
                         esp_rom
                         esp_event
                         nvs_flash
                         driver
                         pthread
                         esp_app_format
                         spiffs
                         esp_adc
                         libsodium
)

#https://docs.espressif.com/projects/esp-idf/en/latest/esp32/api-reference/storage/spiffs.html#tools
#Flashes the webapp files to the flash storage.
spiffs_create_partition_image(www ../automaticPetFeederWebapp/Static FLASH_IN_PROJECT)