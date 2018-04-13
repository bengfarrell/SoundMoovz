# Device API
## Advertise
Advertise with the following name.

* format: `<Model number> <Address without :>`
* Model number: `BMZ001<Color>`
* Example: `BMZ001BK 0123456789AB`

Color information is as below.

| Model | Color |
| --- | --- |
| BK | Black |
| NB | Navy Blue |
| PK | Pink |
| PU | Purple |


## Predefined Services
* [Device Information Service](https://www.bluetooth.com/specifications/gatt/viewer?attributeXmlFile=org.bluetooth.service.device_information.xml)


## Device Control Service
When you shake the device, the characteristic is updated.

UUID
: `E89EFDDA-AD17-43D5-8CA9-08024534606D`

### Accelerometer
UUID
: `6BCA21D1-521D-4548-BF0B-208CF8CC8E9F`

#### Properties
* Read
* Notify

#### Value
##### Data mapping
<table>
<tr><th>bit 7</th><th>bit 6</th><th>bit 5</th><th>bit 4</th><th>bit 3</th><th>bit 2</th><th>bit 1</th><th>bit 0</th><th></th></tr>
<tr><td colspan="8">Sequence number</td><td>0x0000</td></tr>
<tr><td colspan="8">State</td><td>0x0001</td></tr>
<tr><td colspan="8">Value X (bit 9 ~ 2)</td><td>0x0002</td></tr>
<tr><td colspan="2">Value X (bit 1 ~ 0)</td><td colspan="6">blank</td><td>0x0003</td></tr>
<tr><td colspan="8">Value Y (bit 9 ~ 2)</td><td>0x0004</td></tr>
<tr><td colspan="2">Value Y (bit 1 ~ 0)</td><td colspan="6">blank</td><td>0x0005</td></tr>
<tr><td colspan="8">Value Z (bit 9 ~ 2)</td><td>0x0006</td></tr>
<tr><td colspan="2">Value Z (bit 1 ~ 0)</td><td colspan="6">blank</td><td>0x0007</td></tr>
</table>

##### Data description

| Name | Type | Lower limit | Upper limit | Description |  
| --- | --- | --- | --- | --- |  
| Sequence number | Unsigned int | 0 | 8 bit | Sequential number for detect missing. If it is other than the previous value + 1, a missing has occurred. Next to 255 is 0. |  
| State |  |  |  | Not used |  
| Value X | int | 10 bit | 10 bit | X axis value of accelerometer |  
| Value Y | int | 10 bit | 10 bit | Y axis value of accelerometer |  
| Value Z | int | 10 bit | 10 bit | Z axis value of accelerometer |  

#### Descriptors
* [Client Characteristic Configuration](https://www.bluetooth.com/ja-jp/specifications/gatt/viewer?attributeXmlFile=org.bluetooth.descriptor.gatt.client_characteristic_configuration.xml)

### Threshold
Adjust the sensitivity of the accelerometer.  
(The threshold value has been reset to the default value after turning on the power)

UUID
: `D4ED748D-49F2-4ADE-A8C5-9FBA70E68EFB`

#### Properties
* Read
* Write

#### Value
##### Data description

| Name | Type | Lower limit | Upper limit | Description |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| Threshold | Unsigned int | 0 | 7 bit |  |

