# WebView APK 文件说明

## 目录结构

内置的 WebView APK 文件应该放在此目录下（`app/src/main/assets/`）。

## 如何获取 WebView APK

### 从 APKMirror 下载（推荐）

APKMirror 是一个可靠的 Android APK 下载站点，已测试可用：

1. **访问 APKMirror**: https://www.apkmirror.com/
2. **搜索 WebView**:
   - 搜索 "Android System WebView"
   - 或直接访问: https://www.apkmirror.com/apk/google-inc/android-system-webview/
3. **选择版本和架构**:
   - 推荐版本: `122.0.6261.64`（已验证可用）
   - 选择对应的架构：
     - `arm64-v8a` - 大多数现代设备（推荐）
     - `armeabi-v7a` - 32位 ARM 设备
     - `x86` - 模拟器
     - `x86_64` - 64位模拟器
4. **下载 APK**: 下载后放到此目录（`app/src/main/assets/`）

## 文件命名规则

APK 文件名必须与代码中 `UpgradeInfo` 的 `url` 字段完全匹配。

例如，对于 `122.0.6261.64` 版本的 `arm64-v8a` 架构：
- 文件名: `com.google.android.webview_122.0.6261.64-626106401_minAPI26_maxAPI28(arm64-v8a,armeabi-v7a)(nodpi)_apkmirror.com.apk`

## 注意事项

1. **文件大小**: WebView APK 文件通常较大（100-200MB），会增加应用体积
2. **架构匹配**: 确保下载的 APK 架构与目标设备匹配
3. **版本兼容**: 确保 APK 的 `minSdkVersion` 不超过设备的 Android 版本
4. **不压缩**: `build.gradle` 中已配置 `noCompress "apk"`，确保 APK 不会被压缩

## 推荐配置

- **推荐版本**: `122.0.6261.64`（已验证可用，支持 H.265 硬件解码）
- **推荐架构**: `arm64-v8a`（覆盖大多数现代设备）
- **多架构支持**: 如果需要支持多种架构，可以下载多个 APK 文件
