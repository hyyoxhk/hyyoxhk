# 驱动部分: 

## bluetooth 部分

1. 调试过博通的蓝牙 bcm43438 (compatible = brcm,bcm43438-bt), 但是蓝牙协议栈和驱动注册流程为分析

2. 调试过博通的蓝牙 ap6275s, wifi蓝牙一体的模块, 简单看过驱动流程, 但是未详细分析 (主要是不是主线代码, 实在太烂)

## dma 部分

1. 详细分析过 xilinx_dma (compatible = xlnx,axi-dma-1.00.a), 并熟知dma proxy, 到应用层调用dma接口的流程

## gpio 部分

1. 调试过 pca953x 驱动 (compatible = nxp,pca9534), 这是一个i2c接口的gpio拓展芯片, 大致浏览过全部驱动代码 (标准驱动, 十分简单)

## drm 部分

1. 读过好几遍 imx 和 stm 和 exynos 目录的gpu驱动代码, 大致了解 drm 架构的启动流程, 熟悉 weston -> libGL -> libdrm -> drm driver 的流程, 但是具体的渲染图形的原理不清楚(缺乏计算机图形专业的知识)

2. 目前只会写一些panel的代码, 以及知道如何配置panel-simple, 适配通用的屏

3. 调试过 otm8009a (compatible = orisetech,otm8009a), 也会根据手册写panel驱动

## i2c 部分

1. 看过 i2c-imx 驱动 (compatible = fsl,imx21-i2c), 并详细看过整个i2c子系统的注册流程, 知道host和device的分层思想

## input 部分

1. 详细分析过 gpio_keys 驱动 (compatible = gpio-keys), 并详细看过input子系统的注册流程, 知道应用层如何调用input子系统接口

2. 详细分析过 goodix 驱动 (compatible = goodix,gt911), 这是一个i2c接口的触摸屏驱动, 知道怎么获取坐标，怎么上报input等

## irqchip 部分

1. 详细分析过 irq-xilinx-intc 驱动 (compatible = xlnx,xps-intc-1.00.a), 通过配合gpio_key驱动, 详细了解 fpga 产生中断到 zynq芯片捕获的全部流程(需要结合代码回忆才行)

## led 部分

1. 分析过几遍 leds-gpio 驱动 (compatible = gpio-leds), 这个驱动是内核标准led驱动, 会熟练配置使用, 但对led子系统还比较模糊

## media 部分

1. 之前3.x版本的内核有分析过v4l2子系统的流程, 并调试过 gc0308 和 hm2131, 但是内核版本变动后, 架构也有所变动, 新增了些isp之类的, 目前还为详细分析此流程, 仅仅调试过ov8858, 暂时还未分析ov8858的流程

## misc 部分

1. 调试并熟读过 at24 驱动 (compatible = atmel,24c02), 并了解结合nvmem 子系统知道怎么将eeprom中的mac地址传给网卡

## mmc 部分

1. 大致看过dw_mmc-exynos mmci_stm32_sdmmc sdhci sdhci-esdhc-imx的驱动, 也大致了解mmc子系统的注册流程, 主要是有些设备树属性Documentation描述不清

## net 部分

1. 看过几遍 stmmac 源码, 知道各种方法配置mac, 知道如何配置phy, 包括移植phy, 调试网口phy (YT8511)

2. 详细分析过 enc28j60 驱动 (compatible = microchip,enc28j60), 这是个spi接口的网卡驱动, 内核标准驱动, 可以了解到上层的skb怎么传到硬件的全过程

## nvme 部分

1. 读过几遍nvmem子系统的调佣流程, 知道stmmac驱动是如何调用nvme接口获取eeprom中的mac

## pci 部分

1. 只会配置和使用, 未读过相关的驱动源码

## phy 部分

1. 未详细读过此部分的源码, 只在调试usb, video, 摄像头部分时通过阅读源码获取相关设备树属性配置(Documentation描述不清)

## pinctrl 部分

1. 4.x版本内核是详细读过pinctrl子系统, 了解内核io引脚复用的原理, 以及知道各个平台是如何配置pinctrl的

## pwm 部分

1. 4.x版本读过 pwm-samsung 和 pwm-imx27 驱动源码, 知道pwm的host端的注册流程, 也知道其他驱动如何调用pwm接口

## rtc 部分

1. 熟读 rtc-1382 驱动, 并了解rtc子系统的注册流程, 以及知道如何调用上层接口

## spi 部分

1. 详细分析过 spidev 驱动 (compatible = rohm,dh2228fv), 这是一个spi用户层接口, 知道如何通过spi用户层接口于spi外设通信

2. 详细分析过 驱动 spi-gpio (compatible = spi-gpio), 这是一个标准的gpio模拟spi接口的驱动, 熟练使用

3. 读过几遍 spi-imx 和 spi-s3c64xx和 spi-stm32, 知道spi的master的注册流程, 以及了解spi设备端传数据到spi master端写数据到控制器的流程

## usb 部分

1. 大致了解usb host和usb 从机的分层模型, 但是usb具体的协议不清楚, 目前只会调试使用

## video 部分

1. 目前只会适配backlight部分, 并了解backlight的流程及使用和配置backlight
