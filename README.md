# 铠甲勇士激斗传 Android 移植工程

- 原始 SWF 已放入 `app/src/main/assets/game.swf`
- 横屏全屏 WebView 容器
- Ruffle Web 播放核心通过官方 npm CDN 加载（首次启动需要联网）
- 屏幕虚拟键：左、右、攻击（Control）、跳跃（Space）

## 编译

使用 Android Studio 打开本目录，安装 Android SDK 35，然后执行：

```bash
./gradlew assembleDebug
```

APK 输出：`app/build/outputs/apk/debug/app-debug.apk`

## 说明

本环境没有 Android SDK / Android Gradle 构建工具，也无法联网下载 Ruffle Web 的 JS/WASM 文件，因此没有在此生成或验证 APK。当前工程需要联网从 `https://unpkg.com/@ruffle-rs/ruffle@0.8.0/` 加载 Ruffle。SWF 本体在 APK 内置。游戏实际键位若与默认方向键、Control、Space 不同，需要根据游戏响应键位调整 `index.html` 中的虚拟按键映射。
