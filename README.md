# Zabbix PAC3200 - Power Meter template

This template is for the Siemens PAC3200 power meter. It uses the Modbus protocol to communicate with the device. Uses the official [Agent 2 Modbus integration](https://www.zabbix.com/integrations/modbus) (formerly used the [libzbxmodbus](https://github.com/v-zhuravlev/libzbxmodbus)).

Requires the following macros to be set on the host:

- `{$MODBUS_ENDPOINT}` - Modbus endpoint to fetch data from. Example: `192.168.10.10:502`

## Example host

Each powermeter needs to be defined as separate host as this template does not use Zabbix LLD.

Host name: Powermeter 1

Templates: Template PAC3200 Powermeter modbus

Interfaces:

  - agent: 127.0.0.1 (uses zabbix host agent for discovery), Connect to: IP, Port: 10050

Description: "IP set by {$MODBUS_ENDPOINT} macro" (just as a reminder that connection is not set by interfaces, but macro)
