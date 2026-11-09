# Android Key 配置

在高德开放平台为自己的 Android 包名与**最终 APK 实际签名 SHA1**创建客户端 Key，并具备所需商业许可和服务权限。不要复用作者测试 Key、签名或 Web 服务 SecretKey。

宿主在用户明确同意后通过 initializeAMapMap({ key: 本机配置的客户端Key, privacyAgreed: true, ...回调 }) 传入。插件已通过 SDK API 设置地图、导航、定位与搜索的 Key，真实独立 QA 包未附带 Manifest Key 即运行成功。若宿主同时集成其他要求 Manifest 元数据的高德能力，请统一配置并确保两处一致。

新增原生依赖需要自定义基座；普通标准基座不能替代正式集成。SDK 依赖固定版本见接入文档，不能重复添加 AMap3DMap 或其他版本。

实际 Key 保存在宿主受控本机配置中，不写入公开示例、Git 历史或聊天。SDK 客户端 Key 不作为服务端 Secret 使用；限制包名和签名。
