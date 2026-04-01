# DM-FC01

DM-FC01 是达妙第一个飞控项目，当前硬件版本为测试版，后续硬件设计和相关文档都可能调整。  
DM-FC01 is the first flight controller project. The current hardware revision is a beta/test version, and both the hardware design and documentation may change in future revisions.

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

## ArduPilot 源码 / ArduPilot Source

`ardupilot/` 目录正在整理中，相关内容后续补充。  
`ardupilot/` is being organized. Details will be added later.
