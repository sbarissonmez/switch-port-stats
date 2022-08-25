## Switch Port Stat with Scrapli

This is an example script that makes use of Scrapli & Cisco genie to parse CLI output from an IOS-XE device.

The purpose of this script is to:

    1. Connect to one or more devices (Specified in config.yml)
    2. Pull a 'show version' & 'show interfaces' using Scrapli
    3. Use Genie to parse the output
    4. Collect stats on total ports, used ports, port speed / media types, etc
    5. Write out this data to a spreadsheet

-----------------------

## Usage

`config.yml` - This file contains a list of devices. Specify the hostname, username, and password for each device. Note: device type is not currently used

`switchport_stats.py` - After filling in the config file, run this script to collect data from each device specified in config.yml

-----------------------

## Sample Output

For example, running the complete script against my lab Catalyst 9200 switch would output the following:

Hostname  | Model         | Serial Number | Software Version | Total Interfaces | Interfaces UP (Total) | Interfaces DOWN (Total) | Interfaces Disabled | Interface Operational Speed (10M) | Interface Operational Speed (100M) | Interface Operational Speed (1G) | Interface Operational Speed (10G) | Interface Media (Copper) | Interface Media (SFP) |
-- | -- | -- | -- | -- | -- | -- | -- | -- | -- | -- | -- | -- | -- |
SW-C9200  | C9200L-24T-4X | XX########X | 16.9.4 | 28 | 7 | 8 | 13 | 0 | 1 | 6 | 0 | 24 | 4 |

