
*Please :star: this repo if you find it useful*

# Average Sensor for Home Assistant

[![GitHub Release][releases-shield]][releases]
[![GitHub Activity][commits-shield]][commits]
[![License][license-shield]](LICENSE.md)

[![hacs][hacs-shield]][hacs]
[![Project Maintenance][maintenance-shield]][user_profile]
[![Support me on Patreon][patreon-shield]][patreon]

[![Community Forum][forum-shield]][forum]


This repository provides a set of blueprints for Home Assistant to generate an Energy Managment System (EMS) for your home. The focus today is on Charging electical vehicels including a Surplus charging capabilities for those who want to leverage their Solar engery at home. The scripts works independently but needs to be set up in a way that helper entities are used.


# The Blueprints 

## Type Change blueprint
This is the default script you will need to use if you start with your automation. This script makes sure to adopt the different settigns based on a Charging Type - a helper entity - that contains the following Options (Default, Trip, Surplus, Morning-Min and Stop). 


[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fraw.githubusercontent.com%2Fgsaurer%2Fha-ems%2Fmain%2Fblueprints%2FEMS%2FEMS-Car-Charging-TypeChanged.yaml)

![EMS-Car-Charging-TypeChanged](https://github.com/gsaurer/ha-ems/assets/2656836/bd132bc2-c6cb-4d79-a2b6-fa59dfbcf558)


## Surplus blueprint
If Surplus is activate this script runs every 5 seconds to set the correct current value on the charger based on a potential power mean. To create a mean power sensor use the [ha-average Extension](https://github.com/Limych/ha-average) Idealy you set a 5 min window on it to smooth peaks for the charger. 


Example configuration.yaml entry for the average sensor
```yaml
sensor:
  - platform: average
    name: "[EMS] - [Car] - Potential Power mean
    unique_id: ems_car_potential_power_mean
    entities:
      - sensor.ems_car_potential_power_now
    duration: 00:05:00
```

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fraw.githubusercontent.com%2Fgsaurer%2Fha-ems%2Fmain%2Fblueprints%2FEMS%2FEMS-Car-Charging-Surplus.yaml)

![EMS-Car-Charging-Surplus](https://github.com/gsaurer/ha-ems/assets/2656836/b84f2588-8b89-4016-a721-20b5b44099cf)


## Surplus Morning-Minimum

If you are using Surplus charging by default this script will make sure that you have at least a certain battery level in the morning when you want to leave. 

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fraw.githubusercontent.com%2Fgsaurer%2Fha-ems%2Fmain%2Fblueprints%2FEMS%2FEMS-Car-Charging-Surplus-MorningMin.yaml)

![EMS-Car-Charging-Surplus-MorningMin](https://github.com/gsaurer/ha-ems/assets/2656836/a5f97be9-bdb0-408e-8278-0728ac1fe496)


## Surplus go-e ECO

This is only usefull for go-e charger owners that want to use the ECO mode. It publishes the avaialbe power over mqtt to the go-e charger. For this the [home-assistant-goecharger-mqtt Extension](https://github.com/syssi/homeassistant-goecharger-mqtt) is needed. As the charger is not really taking those values into account it's a nice to have but not neccesary. 

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fraw.githubusercontent.com%2Fgsaurer%2Fha-ems%2Fmain%2Fblueprints%2FEMS%2FEMS-Car-Charging-Surplus-go-e-ECO.yaml)

![EMS-Car-Charging-Surplus-go-e-ECO](https://github.com/gsaurer/ha-ems/assets/2656836/4b31318e-5a9e-49cc-acb8-13314161f0e3)


## Trip Calendar Entry

Based on entries within a selectable callendar in Home assitant this script makes sure that your battery reaches a configurable state before you have to leave. You can leverage any calendar e.g. the [Google Calendar Integration](https://www.home-assistant.io/integrations/google/).

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fraw.githubusercontent.com%2Fgsaurer%2Fha-ems%2Fmain%2Fblueprints%2FEMS%2FEMS-Car-Charging-Trip-Calendar.yaml)

![EMS-Car-Charging-Trip-Calendar](https://github.com/gsaurer/ha-ems/assets/2656836/736a0858-6e0a-4182-b48e-c18f1acc5308)

