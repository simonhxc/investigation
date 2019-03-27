#DCM缓存逻辑
- 现在的缓存有
   - device缓存
   - Point缓存？
   - IMemoryCache依赖注入使用缓存机制
   - influxDB配置缓存

传递过来的数据
```
[
   { 
      "DeviceNo":"No1", 
      "Timestamp":"2019", 
      "Points":{
         "Code1":1.1, 
         "Code2":1.2,
         ...
      }
   },
   ...
]
```

   1. `new UploadFullSettings`，在创建对象的时候，传入构造函数参数，完成influxDB信息初始化
   2. `this.MapDevices`方法，初始化设备信息,码点信息
   3. 遍历接收的设备码点数据数组
   4. 判断接收的设备编号是否为null或空字符串
   5. 判断接收的设备编号是否存在于缓存设备字典中（判断数据库是否已经添加该设备）
   6. ~~判断TenantId是否一致~~(因为是从单一租户获取的设备信息)
   7. ~~判断设备是否启用~~（Enable字段被删除）
   8. 尝试添加数据到influxDB
   9. 遍历Points,判断接收的码点编号是否在Device的Mapping中（核对码点和设备是否对应）
   10. tag使用device和code


问题：
1. 现在是把FullSetting整个对象存入MemoryCache,以byzan.context.tenantID作为Key值
2. 需要确认一下是否在内存中记录的都要放入MemoryCache?
3. 码点保存时，原来的代码有尝试使用target作为fieldName保存？对应现在结构中的用户字典？？
4. influxDB数据库保存，field不适合作为查询条件，应该把码点信息作为tag存入？
5. 原来的代码，码点名是作为列名存入的？
6. 设备添加和码点添加要开放给第三方？