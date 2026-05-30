# HAL_0_BlinkingLED

## 简介
本项目为基于硬件抽象层（HAL）的单片机示例：LED 闪烁（Blinking LED）。用于演示如何使用 HAL 接口配置 GPIO 并通过定时器或延时实现简单的 LED 闪烁功能。

## 主要功能
- 配置 GPIO 输出引脚驱动 LED
- 使用阻塞延时或硬件定时器切换 LED 状态
- 结构清晰，便于移植到不同 MCU 平台

## 硬件要求
- 一块支持 HAL 的微控制器开发板（例如 STM32、GD32 等），此项目使用STM32F103C8T6
- 一只 LED（及限流电阻），连接到指定 GPIO 引脚，此处为最小系统开发板板载LED

## 软件依赖
- STM32CubeMX
- HAL 库（对应目标芯片的官方 HAL 或兼容实现）
- 常见交叉编译工具链（如 arm-none-eabi-gcc）
- 固件烧录工具（如 ST-Link）

## 构建与运行
1. 使用对应 MCU 的 HAL 库初始化工程文件。
2. 配置项目的引脚定义，确认 LED 所连接的端口和引脚。
3. 使用工具链编译并生成固件（例如 .bin 或 .hex）。
4. 使用烧录工具将固件写入目标板并重启。

示例（通用流程）:

```bash
# 配置工具链后编译
make
# 烧录（示例）
st-flash write build/firmware.bin 0x8000000
```

## 目录结构
- src/           : 源代码
- inc/           : 头文件
- hal/           : HAL 层实现或适配代码
- board/         : 板级配置
- CMakeLists.txt : CMake清单
- HAL_0_BlinkingLED.ioc ： STM32CubeMX配置文件

## 许可
本仓库采用 MIT License。

## 作者
项目维护者：Sun Yi

## 贡献
欢迎提交 issue 或 pull request，用于修复 bug 或改进示例。
