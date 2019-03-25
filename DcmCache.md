#DCM缓存逻辑
- 现在的缓存有
   - device缓存
   - Point缓存？
   - IMemoryCache依赖注入使用缓存机制
   - influxDB配置缓存

现在是把FullSetting整个对象存入MemoryCache,以byzan.context.tenantID作为Key值

需要确认一下是否在内存中记录的都要放入MemoryCache?