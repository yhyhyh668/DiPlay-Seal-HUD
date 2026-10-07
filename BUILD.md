# 对应源码与构建

完整应用源码来自发布附件 DiPlay-0.2.10-Seal-HUD-Test2-source.zip，请解压后进入 DiPlay-0.2.10 目录。仓库根目录中的差异文件只用于查看，不代替源码包。

环境：JDK 25、Android SDK 37、NDK 28.2.13676358、项目内 Gradle wrapper。

源码测试／无认证资源的调试构建：

```sh
./gradlew :shared:testDebugUnitTest :common:testDebugUnitTest :mobile:lintDebug :mobile:assembleDebug
```

此归档的 debug 变体对应 com.shihab.diplay.sealhud、0.2.10-seal-hud-test2。没有本地认证资源时，assembleDebug 的结果不是可以独立连接 iPhone 的车机包。

原构建记录为 73 项 HUD 相关测试通过。本次发布整理未重跑测试，也未对安装包做改动。

需要独立车机测试包时，由构建者自行提供合法可用的本地运行时认证资源，通过 DIPLAY_AUTH_ASSETS_DIR 明确指定，再使用 :mobile:assembleStandaloneDebug；打包流程见源码 docs/BUILD.md 或本仓库 BUILD-UPSTREAM.md。公开源码不包含配件身份或 Android 签名私钥。

上游预览 APK 中的实验性身份保持不变；本发布 APK 中这两项资源已与上游公开 0.2.10 APK 核对一致。它们不属于本项目重新签发的 Apple MFi 身份，不在源码许可下重新授权。保留上游第三方声明。

安装包使用本地 debug 签名；源码构建可能产生不同签名，不能直接覆盖已安装的发布包。不分发 Android 签名私钥。
