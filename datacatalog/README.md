## Data Model



### Breakout Garden Sensors

````
{
 "type": "record",
 "name": "breakoutsensor",
 "fields": [
  {
   "name": "uuid",
   "type": [
    "null",
    "string"
   ]
  },
  {
   "name": "ipaddress",
   "type": [
    "null",
    "string"
   ]
  },
  {
   "name": "cputempf",
   "type": [
    "null",
    "int"
   ]
  },
  {
   "name": "runtime",
   "type": [
    "null",
    "int"
   ]
  },
  {
   "name": "host",
   "type": [
    "null",
    "string"
   ]
  },
  {
   "name": "hostname",
   "type": [
    "null",
    "string"
   ]
  },
  {
   "name": "macaddress",
   "type": [
    "null",
    "string"
   ]
  },
  {
   "name": "endtime",
   "type": [
    "null",
    "string"
   ]
  },
  {
   "name": "te",
   "type": [
    "null",
    "string"
   ]
  },
  {
   "name": "cpu",
   "type": [
    "null",
    "float"
   ]
  },
  {
   "name": "diskusage",
   "type": [
    "null",
    "string"
   ]
  },
  {
   "name": "memory",
   "type": [
    "null",
    "float"
   ]
  },
  {
   "name": "rowid",
   "type": [
    "null",
    "string"
   ]
  },
  {
   "name": "systemtime",
   "type": [
    "null",
    "string"
   ]
  },
  {
   "name": "ts",
   "type": [
    "null",
    "int"
   ]
  },
  {
   "name": "starttime",
   "type": [
    "null",
    "string"
   ]
  },
  {
   "name": "BH1745_red",
   "type": [
    "null",
    "float"
   ]
  },
  {
   "name": "BH1745_green",
   "type": [
    "null",
    "float"
   ]
  },
  {
   "name": "BH1745_blue",
   "type": [
    "null",
    "float"
   ]
  },
  {
   "name": "BH1745_clear",
   "type": [
    "null",
    "float"
   ]
  },
  {
   "name": "VL53L1X_distance_in_mm",
   "type": [
    "null",
    "float"
   ]
  },
  {
   "name": "ltr559_lux",
   "type": [
    "null",
    "float"
   ]
  },
  {
   "name": "ltr559_prox",
   "type": [
    "null",
    "float"
   ]
  },
  {
   "name": "bme680_tempc",
   "type": [
    "null",
    "float"
   ]
  },
  {
   "name": "bme680_tempf",
   "type": [
    "null",
    "float"
   ]
  },
  {
   "name": "bme680_pressure",
   "type": [
    "null",
    "float"
   ]
  },
  {
   "name": "bme680_humidity",
   "type": [
    "null",
    "float"
   ]
  },
  {
   "name": "lsm303d_accelerometer",
   "type": [
    "null",
    "string"
   ]
  },
  {
   "name": "lsm303d_magnetometer",
   "type": [
    "null",
    "string"
   ]
  }
 ]
}


````

### Example Data

````

{'uuid': 'snr_20220223215110', 'ipaddress': '192.168.1.229', 'cputempf': 115, 'runtime': 11, 'host': 'piups', 'hostname': 'piups', 'macaddress': 'b8:27:eb:4a:4b:61', 'endtime': '1645653070.9452138', 'te': '11.110888481140137', 'cpu': 6.5, 'diskusage': '3975.5 MB', 'memory': 20.4, 'rowid': '20220223215110_21e1c962-4ab3-45a9-90bc-65b783c0d7cc', 'systemtime': '02/23/2022 16:51:11', 'ts': 1645653071, 'starttime': '02/23/2022 16:50:59', 'BH1745_red': 195.8, 'BH1745_green': 140.0, 'BH1745_blue': 100.8, 'BH1745_clear': 160.0, 'VL53L1X_distance_in_mm': 747.0, 'ltr559_lux': 17.18, 'ltr559_prox': 0.0, 'bme680_tempc': 28.17, 'bme680_tempf': 82.71, 'bme680_pressure': 1012.14, 'bme680_humidity': 36.838, 'lsm303d_accelerometer': '-00.03g : -01.01g : -00.00g', 'lsm303d_magnetometer': '+00.08 : +00.40 : +00.05'}

````

##
