# Structure

This repository provides a set of blueprints for Home assistant to generate an Energy Managment System (EMS) for your home. The focus today is on Charging electical vehicels including provide Surplus charging capabilities for thos who have Solar Panels at home. The scripts work independently but need to be set up in a way that helper entities are used.


## The different Scripts

### Type Change blueprint
This is the default script you will need to use if you start with your automation. This script makes sure to adopt the different settigns based on a Charging Type - a helper entity that contains the following Options (Default, Trip, Surplus, Morning-Min and Stop). 

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fraw.githubusercontent.com%2Fgsaurer%2Fha-ems%2Fmain%2Fblueprints%2FEMS%2FEMS-Car-Charging-TypeChanged.yaml)


### Surplus blueprint

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fraw.githubusercontent.com%2Fgsaurer%2Fha-ems%2Fmain%2Fblueprints%2FEMS%2FEMS-Car-Charging-Surplus.yaml)

### Surplus Morning minimum

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fraw.githubusercontent.com%2Fgsaurer%2Fha-ems%2Fmain%2Fblueprints%2FEMS%2FEMS-Car-Charging-Surplus-MorningMin.yaml)

### Surplus go-e ECO

This is only usefull for go-e charger owners that want to use the ECO mode. 

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fraw.githubusercontent.com%2Fgsaurer%2Fha-ems%2Fmain%2Fblueprints%2FEMS%2FEMS-Car-Charging-Calendar.yaml)

### Trip Calendar Entry

Based on calendar entries starts the charging to make sure you have a certain battery % at the time you leave. 

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fraw.githubusercontent.com%2Fgsaurer%2Fha-ems%2Fmain%2Fblueprints%2FEMS%2FEMS-Car-Charging-Calendar.yaml)



## The Helpers

lorem ipsum
