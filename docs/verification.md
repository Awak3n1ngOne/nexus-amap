# 1.0.0 验证范围

日期：2026-11-09。Android 独立 Native QA 宿主：com.nexus.amapqa；Redmi 22101317C、Android 14。固定深圳 GCJ02 起终点，不获取手机 GPS，截图不是设备实时位置。

- 真实地图可见，SDK 返回 3 条驾车路线。
- 路线 12：3843 米 / 780 秒；13：5419 米 / 960 秒；14：3854 米 / 900 秒。数值是本次服务回包，不代表未来路况承诺。
- SDK 实际开始模拟导航；21 次导航进度、21 个不同的剩余距离/时间/步骤状态；随后真实 onStopNavi 停止事件。
- 8 个 Native 接口回调均一次、主线程、code=0；没有超时或生命周期中断。语音关闭，不声称可听语音验收。
- 1677 个 SDK 资源与 ARM32/ARM64 各 7 个 SO 完整进入 APK。
- HBuilderX 5.34 uvue、Vue3 nvue、Vue2 nvue 消费者编译通过。
- iOS 13.4 arm64 真实 SDK/四个厂商 Framework、公开 UTS 与组件生成代码、实际 DCloud Runtime 类型检查与链接通过；不是 iPhone 真机验收。
- 离线 Kotlin 36/36、Swift 38/38；Android 几何 18/18、Swift 几何 23/23；双插件离线存储隔离通过。
- 独立源码审查完成，修正平台事件、策略、途经点与坐标来源等问题。

尚未验收：UTS/uvue/nvue 真机页面、iOS 真机及签名包、iOS HBuilder CocoaPods 自动原生构建、实时 GPS/连续定位、真实 POI/地址解析、货车商业服务、步行/骑行真机导航、物理可听语音、多机型长期稳定性。Native QA 不能替代上述项目。

真实实现依赖使用者自己的 Key、服务授权与配额。公开仓库不含实际 Key、SDK 二进制、签名或 APK。
