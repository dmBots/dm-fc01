# DM-FC01

DM-FC01 是达妙第一款正式量产的飞控产品。本文档对应当前出货的硬件版本，适用于用户首次拿到产品后的接线、配置与使用。  
DM-FC01 is Damiao's first mass-produced flight controller product. This documentation applies to the current shipping hardware revision and is intended for initial wiring, setup, and use after receiving the product.

## 文档 / Documentation

- 用户手册：[docs/DM-FC01用户手册.md](docs/DM-FC01用户手册.md)  
  User manual: [docs/DM-FC01用户手册.md](docs/DM-FC01用户手册.md)
- 引脚定义：[docs/DM-FC01_pinout.xlsx](docs/DM-FC01_pinout.xlsx)  
  Pin definition: [docs/DM-FC01_pinout.xlsx](docs/DM-FC01_pinout.xlsx)

## PX4 源码 / PX4 Source

`PX4-Autopilot/` 目录中存放适配 DM-FC01 的 PX4 源码。  
`PX4-Autopilot/` contains the PX4 source adapted for DM-FC01.

不同 PX4 版本通过不同分支维护。如需单独拉取某个适配版本，可直接克隆对应分支，例如：  
Different PX4 versions are maintained through branches. To pull a specific adapted version directly, clone the target branch, for example:

```bash
git clone --branch damiao_dm-fc01_v1.14.0 --recursive https://github.com/CaFeZn/PX4-Autopilot.git
```

参考分支 / Reference branch:

- `damiao_dm-fc01`
- `damiao_dm-fc01` 目前跟随最新 PX4 主线开发，用于在完整测试完成后向 PX4 官方提交 PR。出厂固件默认使用该分支。  
  `damiao_dm-fc01` tracks the latest PX4 upstream mainline and is intended for an eventual PR to the official PX4 repository after full validation. Factory firmware ships with this branch by default.
- `damiao_dm-fc01_v1.14.0`
- https://github.com/CaFeZn/PX4-Autopilot/tree/damiao_dm-fc01_v1.14.0

其他 PX4 版本仍在适配中，暂时留空。  
Other PX4 version branches are still being adapted and are not listed yet.

补充说明 / Additional note:

- 相比 PX4 v1.14、v1.15、v1.16 原版版本，DM-FC01 适配分支仅修改了 `heater` 模块以适配双 IMU 加热器，以及 `board` 板级代码，其他部分均无改动。  
  Compared with upstream PX4 v1.14, v1.15, and v1.16, the DM-FC01 adaptation branches only modify the `heater` module for dual-IMU heater support and the board-level code. No other parts are changed.
- 多加热器支持可参考 PX4 上游 PR `#26325`：https://github.com/PX4/PX4-Autopilot/pull/26325  
  For multi-heater support, see upstream PX4 PR `#26325` ("Add multi-instance support for heaters", merged on March 2, 2026): https://github.com/PX4/PX4-Autopilot/pull/26325
- 主要启停命令与以前版本保持兼容：  
  The main control commands remain compatible with previous versions:

```bash
nsh> heater status
nsh> heater start
nsh> heater stop
```

- 该 PR 新增了通过 `-i` 参数单独启停某个加热器的能力；在 NSH 控制台输入 `heater` 可查看相关帮助，通常不需要手动指定。  
  The PR also adds per-heater control through the `-i` option. Enter `heater` in the NSH console to see the available help; in normal use, this usually does not need to be changed manually.
- 如需修改温控参数，可在完整参数列表中搜索 `heater` 相关参数后进行调整。  
  If temperature-control behavior needs to be adjusted, search for `heater` in the full parameter list and modify the related parameters there.

## ArduPilot 源码 / ArduPilot Source

`ardupilot/` 目录正在整理中，相关内容后续补充。  
`ardupilot/` is being organized. Details will be added later.
