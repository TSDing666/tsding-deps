# TSDing 依赖仓

TSDing 的私有依赖仓：所有逆向工具链依赖的预编译产物 + CI 构建管线。
产物以 GitHub Release 资产形式托管（单文件上限 2 GB），可由 App 下载管理器直接拉取。

## 拉取方式

Release 地址：https://github.com/TSDing666/tsding-deps/releases/download/deps-v1/<文件名>

私有仓需携带令牌（App 内置配置，勿硬编码进代码）：

```
curl -L -H "Authorization: Bearer <TOKEN>" \
  -o libkeystone.so \
  https://github.com/TSDing666/tsding-deps/releases/download/deps-v1/libkeystone.so
```

注意：gh-proxy 等公共加速代理无法访问私有仓，私有依赖必须直连并带 Authorization 头。
若后续将仓库改为公开，则可复用 gh-proxy/ghfast 竞速线路（与方案文档 22.7 一致）。

## CI 构建

`.github/workflows/build-r2ghidra.yml`（手动触发 workflow_dispatch）：
1. 按 radare2 官方配方（sys/android-ndk-install.sh + sys/android-sdk.sh -a arm64）构建 r2 6.2.0 Android arm64 SDK（含头文件与重定位 pkg-config）
2. meson 交叉编译 r2ghidra 6.2.2（NDK 独立工具链，sleighc 打 native 补丁在 host 编译运行）
3. 产出 `libr2ghidra.so`（arm64 插件）与编译好的 sleigh 数据，上传为 workflow artifact，人工转存 Release

## 文件清单

见 [DEPENDENCIES.md](DEPENDENCIES.md)。
