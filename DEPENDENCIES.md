# 依赖清单（deps-v1 Release 资产）

| 资产文件 | 说明 | 大小 | 来源 |
|---|---|---|---|
| `radare2-6.2.0-android-aarch64.tar.gz` | radare2 6.2.0 官方 Android 安装树 | 22.9 MB | radareorg/radare2 Release |
| `radare2_6.2.0_aarch64.deb` | radare2 6.2.0（Termux 备用源） | 7.6 MB | packages.termux.dev |
| `frida-server-17.18.0-android-arm64.xz` | Frida server 17.18.0（xz） | 17.1 MB | frida/frida Release |
| `jadx-1.5.0.zip` | jadx 1.5.0 完整包 | 100.1 MB | skylot/jadx Release |
| `blutter_android.zip` | Blutter standalone v1.0 | 86.3 MB | AcE77505/blutter-standalone Release |
| `OpenJDK17U-jre_aarch64_linux_hotspot_17.0.20.1_1.tar.gz` | Temurin 17 JRE aarch64 | 43.9 MB | Adoptium |
| `ubuntu-base-22.04-base-arm64.tar.gz` | Ubuntu Base 22.04 rootfs | 26.4 MB | cdimage.ubuntu.com |
| `keystone-0.9.2.tar.gz` | keystone 0.9.2 源码 | 4.2 MB | keystone-engine GitHub |
| `r2ghidra-6.2.2.tar.xz` | r2ghidra 6.2.2 源码 | 3.8 MB | radareorg/r2ghidra Release |
| `r2ghidra_sleigh-6.2.2.zip` | r2ghidra sleigh 数据（287 文件） | 9.9 MB | radareorg/r2ghidra Release |
| `Il2CppDumper-net6-v6.7.46.zip` | Il2CppDumper net6 | 0.4 MB | Perfare/Il2CppDumper Release |
| `Rodroid.Il2cppDumper.v6.1.apk` | Rodroid Rust 版（含 arm64 .so） | 12.5 MB | rodroidmods Release |
| `quickjs-android-0.2.1.aar` | QuickJS aar | 0.9 MB | OpenQuickJS Release |
| `epic-0.11.2.aar` | Epic ART Hook 0.11.2 | 0.1 MB | JitPack (tiann/epic) |
| `dexlib2-2.5.2.jar` | dexlib2 2.5.2 | 1.1 MB | Maven Central |
| `bcprov-jdk18on-1.78.jar` | BouncyCastle 1.78 | 7.9 MB | Maven Central |
| `apksig-8.5.0.jar` | apksig 8.5.0 | 0.5 MB | Google Maven |
| `fastjson2-2.0.51.jar` | fastjson2 2.0.51 | 2.0 MB | Maven Central |
| `slf4j-api-2.0.13.jar` | slf4j 2.0.13 | 0.1 MB | Maven Central |
| `jna-5.13.0.jar` | JNA 5.13.0 | 1.8 MB | Maven Central |
| `pyelftools-0.33-py3-none-any.whl` | pyelftools 0.33 | 0.2 MB | PyPI |
| `frida_dexdump-2.0.1-py3-none-any.whl` | frida-dexdump 2.0.1 | 0.0 MB | PyPI |
| `libkeystone.so` | libkeystone.so 0.9.2 arm64 | 6.0 MB | 本机 NDK 构建（全网无预编译） |
| `libunicorn.so` | libunicorn.so 2.1.4 arm64 | 18.9 MB | Termux 提取 |
| `libunicorn_ndk.so` | libunicorn.so 2.1.4 arm64（NDK 版） | 18.9 MB | 本机 NDK 构建 |
| `libunicorn_java.so` | libunicorn_java.so JNI arm64 | 0.0 MB | 本机 NDK 构建（修上游 bug） |
| `libcapstone.so` | libcapstone.so 5.0.9 arm64 | 8.8 MB | Termux 提取 |
| `libquickjs-android.so` | libquickjs-android.so arm64 | 0.9 MB | aar 提取 |
| `libepic.so` | libepic.so 0.11.2 arm64 | 0.0 MB | aar 提取 |
| `demumble_arm64` | demumble arm64 可执行 | 0.6 MB | 本机 NDK 构建 |
| `librodroid_il2cppdumper.so` | Il2CppDumper Rust 引擎 arm64 | 5.2 MB | Rodroid APK 提取 |
| `frida-server` | frida-server 17.18.0 解压后 | 56.1 MB | xz 解压 |
| `jadx-1.5.0-all.jar` | jadx all-in-one jar | 109.3 MB | zip 提取 |
| `unidbg-android-0.9.9.jar` | unidbg-android（含系统库资源） | 5.9 MB | 本机 Maven 构建 |
| `unidbg-api-0.9.9.jar` | unidbg-api | 0.4 MB | 本机 Maven 构建 |
| `unidbg-unicorn2-0.9.9.jar` | unidbg unicorn2 backend | 5.9 MB | 本机 Maven 构建 |
| `frida-dexdump-agent.js` | frida-dexdump JS Agent | 0.0 MB | wheel 提取 |
| `Il2CppDumper.dll` | Il2CppDumper net6 主程序 | 0.2 MB | zip 提取 |

## Blutter 主路径

Blutter 按需下载主路径为自有仓 **TSDing666/tsding-engines-dyn**（动态链接引擎，91 个 Dart 版本按需 + 共享运行件），本 Release 不再托管 Blutter。

## CI 产物（build-r2ghidra workflow）

| 资产文件 | 说明 | 来源 |
|---|---|---|
| `libr2ghidra.so` | r2ghidra 6.2.2 arm64 插件 | GitHub Actions 交叉编译 |
| `r2ghidra_sleigh-compiled.zip` | CI 编译的 sleigh 数据 | 同上 |

> 自研组件（libdisassembler.so、r2 配置、Lua 反编译器、Cocos 提取器、Godot 解包器）不属于本仓，为 App 开发产物。
