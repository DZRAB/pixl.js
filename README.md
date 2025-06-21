# Pixl.js - Amiibo模拟器开发套件

![Pixl.js设备](https://github.com/solosky/pixl.js/blob/main/assets/pixljs-3.jpg)
![Pixl.js使用示例](https://github.com/solosky/pixl.js/blob/main/assets/pixljs-4.jpg)

## 项目概述

Pixl.js是一个基于nRF芯片的开源硬件项目，主要用于模拟和管理Amiibo NFC标签。本项目是原版[Pixl.js](http://www.espruino.com/Pixl.js)的复刻版本，增加了Amiibo模拟等高级功能。

## 主要特性

- **Amiibo模拟**：支持模拟任天堂Amiibo NFC标签
- **卡片管理**：内置Amiibo数据库，支持分类和搜索
- **多设备支持**：支持Chameleon Ultra卡片模拟
- **蓝牙连接**：通过BLE与手机应用通信
- **游戏功能**：内置多个经典小游戏
- **多语言支持**：支持中文、英文、意大利语等多种语言
- **开源硬件**：提供完整的KiCad设计文件

## 硬件规格

- **主控芯片**：nRF52832/nRF52840
- **显示屏**：128x64 OLED/LCD屏幕
- **NFC**：支持NTAG21X系列标签模拟
- **存储**：内置SPI Flash存储
- **电池**：支持锂电池充放电管理
- **扩展接口**：GPIO、SPI、I2C等

## 软件架构

项目包含三个主要部分：

1. **固件(fw/)**
   - 基于nRF SDK开发
   - 模块化设计，支持多种应用场景
   - 自定义UI框架(MUI)
   - 文件系统支持(VFS)

2. **Web应用(web/)**
   - 基于Vue.js开发
   - 通过BLE与设备通信
   - 提供图形化管理界面

3. **硬件设计(hw/)**
   - 使用KiCad设计
   - 提供多个版本(RevA, RevB)

## 快速开始

### 硬件准备
1. 获取Pixl.js开发板或根据设计文件自行制作
2. 准备USB数据线和锂电池

### 固件烧录
```bash
# 进入固件目录
cd fw
# 编译并烧录
make flash
```

### Web应用使用
```bash
# 进入web目录
cd web
# 安装依赖
npm install
# 启动开发服务器
npm run dev
```

## 文档

- [中文文档](docs/zh/README.md)
- [English Documentation](docs/en/README.md)
- [Italian Documentation](docs/it/README.md)

详细文档包含：
- [硬件指南](docs/zh/01-Hardware.md)
- [固件烧录](docs/zh/02-Flash-Firmware.md)
- [固件编译](docs/zh/03-Build-Firmware.md)
- [使用教程](docs/zh/04-Using-Firmware.md)
- [BLE协议](docs/zh/05+1-ble_protocol.md)

## 贡献指南

欢迎通过以下方式参与贡献：
- 提交Pull Request改进代码
- 报告Issues
- 完善文档
- 参与社区讨论

### 特别感谢
- @Caleeeeeeeeeeeee - 完善的Bootloader
- @白橙 - 制作的外壳
- @impeeza - 提供的文档翻译

## 社区

**国内用户**:
- QQ群: 109761876

**国际用户**:
- [Pixl.js Discord社区](https://discord.gg/4mqeQwcAB2)

## 许可证

本项目基于GPL 2.0 License发布，使用请遵循以下约定：
- 修改后的源码必须公开
- 必须使用相同的License发布

## 声明

本项目为开源项目，仅为学习研究用途，请勿用于商业用途。

Amiibo是任天堂的注册商标，NTAG21X为NXP的注册商标。

内置的Amiibo数据库来源:
- [amiiloop](https://download.amiloop.app/)
- [AmiiboAPI](https://www.amiiboapi.com/)

源代码不包含任何有任天堂版权的资源（如相关密钥、Amiibo原始数据等）。

## 提示

Amiibo无限刷功能需要`key_retail.bin`文件，请将其上传到设备存储根目录后使用。