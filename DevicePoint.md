- 设备表  
   
|列名|类型|是否必填|描述|  
|NO|string|yes|设备编号|  
|Name|string|yes|设备名称|  
|IP|string|no|IP地址|  
|Remark|string|no|备注|  

```
{
    "No":"deviceNo1",
    "Name":"deviceName1",
    "IP":"192.168.1.100",
    "Remark":"设备1"
}
```

- 码点表  
   
|列名|类型|是否必填|描述|  
|No|string|yes|码点编号|  
|Name|string|yes|码点名称|  
|DeviceId|long|yes|设备id|  
|Remark|string|no|备注|  

```
{
    "No":"PointNo1",
    "Name":"PointName1",
    "DeviceId":"123456789"
    "Remark":"设备1下的A码点"
}
```
