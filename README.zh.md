# 骁龙845(sdm845)的EDK2 UEFI固件

![Github](https://img.shields.io/github/downloads/edk2-porting/edk2-sdm845/total)
![Github](https://img.shields.io/github/v/release/edk2-porting/edk2-sdm845?include_prereleases)

**在编译该项目前，请确定你有一定的Linux常识，以下步骤已经是最简单的方法，如果你看不懂，那么请使用Releases中的编译成品**

## 资源

[Telegram交流群](https://t.me/joinchat/MNjTmBqHIokjweeN0SpoyA)

[Discord交流群](https://discord.gg/XXBWfag)

QQ交流群: 697666196 (主群)      737223105 (Linux/edk2)

[Windows 驱动](https://github.com/edk2-porting/WOA-Drivers)

[项目官网](https://renegade-project.org/)

## 警告

**请勿尝试移植到任何索尼和谷歌设备上**

**你的UFS会被清空!!!**

## 已支持的设备

1. 一加6            (enchilada)
2. 一加6T           (fajita)
3. 小米MIX3         (perseus)
4. 小米PocoPhone F1 (beryllium)
5. 魅族16th         (m1882)
6. 锤子坚果R1       (trident)
7. 黑鲨手机一代      (skr-a0)
8. OPPO Find X      (pafm00)
9. 小米MIX2S        (polaris)
10. LG G7           (judyln)
11. 三星S9+         (star2qltechn)
12. 小米7（工程机）  (dipper-old)
13. 小米8           (dipper)
14. 努比亚X         (nx616j)
15. 诺基亚9 PureView(olympic)
16. 华硕 ZenFone 5Z  (draco)

## 依赖

Ubuntu 20.04:

```bash
sudo apt update
sudo apt upgrade
sudo apt install build-essential uuid-dev iasl git nasm gcc-aarch64-linux-gnu abootimg python3-distutils python3-pil python3-git
```

## 构建

**不建议使用Ubuntu 18.04版本，请使用Ubuntu 20.04或以上版本**

1.克隆此项目（默认使用国内fastgit镜像加速）

```bash
git clone https://hub.fastgit.org/edk2-porting/edk2-sdm845.git --depth=1
cd edk2-sdm845
```

2.编译此项目（默认使用fastgit加速submodule克隆，若不需要请删去 `--chinese`）

```bash
bash build.sh --chinese --device DEVICE
```

3.启动镜像

```bash
fastboot boot boot_DEVICE.img
```

(请将DEVICE替换成你的设备代号.)

另外，你可以将UEFI刷写至recovery分区以实现双重启动。

```bash
fastboot flash recovery boot_DEVICE.img
```

## 贡献

感谢`fxsheep`的`edk2-sagit`

感谢`strongtz`维护Renegade Project

感谢`BigfootACA`的编译脚本

感谢`Lemon_Ice`和`NTAuthority`提供指导以及一些有用的blob

感谢`@Freak2112`, `TAO_Croatia`和`废物`的实机调试

感谢`NekokeCore`参与了MemoryMap的修复

## 开源许可证

该项目在[WTFPL LICENSE](http://www.wtfpl.net/)下发布.
