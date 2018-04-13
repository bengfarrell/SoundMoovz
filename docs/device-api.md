# Advertise
以下の名前で Advertise します。

* format: `<型番> <address(:無し)>` (半角space区切り)
* 例: `BMZ001BK 0123456789AB`

型番のColor情報は以下の通りです。

| 型番 | Color |
| --- | --- |
| BK | Black |
| NB | Navy Blue |
| PK | Pink |
| PU | Purple |

# Device Control Service
UUID
: `E89EFDDA-AD17-43D5-8CA9-08024534606D`

## Accelerometer
UUID
: `6BCA21D1-521D-4548-BF0B-208CF8CC8E9F`

### Properties
* Read
* Notify

### Value
#### Data mapping
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

#### Data description

| Name | Type | Lower limit | Upper limit | Description |  
| --- | --- | --- | --- | --- |  
| Sequence number | Unsigned int | 0 | 8 bit | 抜けを検出するための連番。前回の値 + 1 以外の場合、抜けが発生している。 255 の次は 0。 |  
| State |  |  |  | 加速度センサの State の値 |  
| Value X | int | 10 bit | 10 bit | 加速度センサのX軸の値 |  
| Value Y | int | 10 bit | 10 bit | 加速度センサのY軸の値 |  
| Value Z | int | 10 bit | 10 bit | 加速度センサのZ軸の値 |  

### Descriptors
* [Client Characteristic Configuration](https://www.bluetooth.com/ja-jp/specifications/gatt/viewer?attributeXmlFile=org.bluetooth.descriptor.gatt.client_characteristic_configuration.xml)

## Threshold
UUID
: `D4ED748D-49F2-4ADE-A8C5-9FBA70E68EFB`

### Properties
* Read
* Write

### Value
#### Data description

| Name | Type | Lower limit | Upper limit | Description |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| Threshold | Unsigned int | 0 | 7 bit | 感度閾値  |


# Predefined Services
* [Device Information Service](https://www.bluetooth.com/specifications/gatt/viewer?attributeXmlFile=org.bluetooth.service.device_information.xml)

