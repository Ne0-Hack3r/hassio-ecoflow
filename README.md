![hacs_badge](https://img.shields.io/badge/HACS-Custom-41BDF5.svg)
[![Validate with hassfest](https://github.com/vwt12eh8/hassio-ecoflow/actions/workflows/hassfest.yml/badge.svg)](https://github.com/vwt12eh8/hassio-ecoflow/actions/workflows/hassfest.yml)
[![HACS Action](https://github.com/vwt12eh8/hassio-ecoflow/actions/workflows/hacs.yml/badge.svg)](https://github.com/vwt12eh8/hassio-ecoflow/actions/workflows/hacs.yml)
[![CodeQL](https://github.com/vwt12eh8/hassio-ecoflow/actions/workflows/codeql-analysis.yml/badge.svg)](https://github.com/vwt12eh8/hassio-ecoflow/actions/workflows/codeql-analysis.yml)

# EcoFlow Portable Power Station Integration for Home Assistant

This integration uses a local API.
Therefore, if the devices are not on the same network, they cannot synchronize their status.

This integration uses a private API.
Future device updates may prevent integration.

Requires Home Assistant Core 2022.7.0 or later for operation.

## FORK of vwt12eh8/hassio-ecoflow
This version contains fixes required after various updates to HomeAssistant.
It has been tested on Home Assistant OS 16.0 (core 2025.7.3 / supervisor 2025.07.1 / Frontend 20250702.3).
Original code can be found at: https://github.com/vwt12eh8/hassio-ecoflow

### Additions for Delta Pro
These sensors have been added to expand data available from Delta Pro
#### Energy sensors
 - AC input energy
 - AC output energy
 - Car input energy
 - Car output energy
#### Current sensors (amperage)
 - Anderson output current
 - Battery charge current
 - Car output current
 - MPPT output current
#### Voltage sensors
 - Main Batt Voltage
 - Main Batt Min Voltage
 - Main Batt Max Voltage
 - Main Cell Min Voltage
 - Main Cell Max Voltage
 - Extra1 Batt Voltage
 - Extra1 Cell Min Voltage
 - Extra1 Cell Max Voltage
 - Extra2 Batt Voltage
 - Extra2 Cell Min Voltage
 - Extra2 Cell Max Voltage
 - Anderson output voltage
 - Battery charge voltage
 - Car output voltage
 - MPPT output voltage
#### Power sensors (wattage)
 - Main BMS in
 - Main BMS out
 - EB1 BMS in power
 - EB1 BMS out power
 - EB2 BMS in power
 - EB2 BMS out power
 - MPPT output
 - Anderson output
#### Temperature sensors
 - Main cell min temp
 - Main cell max temp
 - Main min mos temp
 - Main max mos temp
 - Extra1 cell min temp
 - Extra1 cell max temp
 - Extra1 min mos temp
 - Extra1 max mos temp
 - Extra2 cell min temp
 - Extra2 cell max temp
 - Extra2 min mos temp
 - Extra2 max mos temp
#### Capacity sensors (Ah)
 - Main battery full capacity
 - Main battery remaining capacity
 - Extra1 battery full capacity
 - Extra1 battery remaining capacity
 - Extra2 battery full capacity
 - Extra2 battery remaining capacity
#### Overall state of charge (%)
 - SOC

## Installation
This integration is not included by default and must be installed by yourself to use it.

Two methods are available, and you can choose one or the other.
- Install as a custom repository via HACS
- Manually download and extract to the custom_components directory

Once installed, after restarting Home Assistant, you can start integration as usual from Add Integration.

## Supported products
- ~~RIVER Mini~~ (Coming soon)
- RIVER Max
- RIVER Pro
  - Extra Battery
- DELTA Mini
- DELTA Max
  - with Extra Battery
- DELTA Pro (Wi-Fi only)
  - with Extra Battery

## How to register for the Energy Dashboard
- MPPT input energy : Solar Panels -> Solar production energy
- total input energy : Home Battery Storage -> Energy going in to the battery
- total output energy : Home Battery Storage -> Energy coming out of the battery

## About Remain Entities
The Remain entity is disabled by default because it is highly variable and generates a large number of writes to the database.

If enabled, it is recommended that these entities be included in the exclude in the recorder settings.
