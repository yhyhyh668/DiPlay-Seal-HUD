# 修改记录

## 0.2.10-seal-hud-test2（版本号 30）

构建与源码归档：2026-10-05。社区发布整理：2026-10-07。

基于 DiPlay v0.2.10；发布安装包与车主已收到的 Test2 完全一致，本次只整理公开说明，没有重新构建。

### HUD 与简易导航

- 新增 BydAmapAdapter，识别指定海豹旧版 com.example.amapservice 系统服务，保留新版 com.byd.amapservice 路径。
- 加入旧服务的 Android package queries 声明，并将“HUD和仪表盘导航”设置的可用性判断接入适配选择器。
- 使用旧原厂服务接收导航广播，解决该车 HUD／仪表简易导航未获得手机提示的问题。
- 补充 SEG_REMAIN_DIS_AUTO、ROUTE_REMAIN_DIS_AUTO、ROUTE_REMAIN_TIME_AUTO 三个旧服务文字字段，修复仪表简易导航距离和剩余时间显示 -1。
- 增加单位格式化；未知值发送空文字；保留原有结束导航处理。
- 应用名称改为 DiPlay Seal HUD；独立包名 com.shihab.diplay.sealhud。
- 新增回归测试，覆盖服务适配条件、真实导航帧到广播字段、未知值及结束状态。

### 小地图／全屏地图

**未修复、未包含完整地图实验。** 这两种仪表模式仍显示原车高德的地图，不会出现手机高德规划的路线。本版传送的是转向、路名、距离等提示数据，不是完整路线几何或地图画面。

### 不包含的其他修改

导航／音乐音量、USB 连接重复确认及后续 Test3／Test4／Test5 地图实验不在本发布包中。

## 差异文件

seal-hud-test2.patch 是开发时保存的差异参考，其调试配置基线与上游原版可能不同，不承诺可直接套用于任意 DiPlay 分支。完整、与 APK 对应的源码以 Release 中的 DiPlay-0.2.10-Seal-HUD-Test2-source.zip 为准。
