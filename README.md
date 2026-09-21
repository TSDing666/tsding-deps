# TSDing 依赖仓

TSDing 的依赖托管仓：所有逆向工具链依赖的预编译产物 + CI 构建管线。
产物以 GitHub Release 资产形式托管（单文件上限 2 GB），可由 App 下载管理器直接拉取。

## 拉取方式

Release 地址：https://github.com/TSDing666/tsding-deps/releases/download/deps-v1/<文件名>

仓库为公开仓，无需令牌即可直连下载：

```
curl -L -o libkeystone.so \
  https://github.com/TSDing666/tsding-deps/releases/download/deps-v1/libkeystone.so
```

国内直连 GitHub 不通时，可套用加速镜像（与方案文档 22.7 多线路竞速一致）：

```
curl -L -o libkeystone.so \
  https://gh-proxy.com/https://github.com/TSDing666/tsding-deps/releases/download/deps-v1/libkeystone.so
```

## CI 构建

`.github/workflows/build-r2ghidra.yml`（手动触发 workflow_dispatch）：
1. 按 radare2 官方配方（sys/android-ndk-install.sh + sys/android-sdk.sh -a arm64）构建 r2 6.2.0 Android arm64 SDK（含头文件与重定位 pkg-config）
2. 用 r2ghidra 6.2.2 发布 tarball（subprojects 已实体化）+ `patches/sleighc-native.patch`（sleighc 以 native 机器编译，供 host 运行生成 .sla）
3. meson 交叉编译（NDK 独立工具链，pkg_config_libdir 限定 target 包），产出 `libcore_r2ghidra.so`（arm64 插件）

产物：`libr2ghidra.so`（strip 后 ~4.8 MB，随 r2 加载）+ 官方 sleigh 数据（deps-v1 已含）。

## 文件清单

见 [DEPENDENCIES.md](DEPENDENCIES.md)。
