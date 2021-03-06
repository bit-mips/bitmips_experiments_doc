# BIT MIPS EXPERIMENTS DOC

> 本仓库文档是为北理工 MIPS 相关实验提供的实验参考手册

## 简介

为更好的方便北理工同学完成 MIPS 相关系列实验，特别提供本参考手册，通过本参考手册可以较好的完成相关实验。

具体实验代码仓库如下：[https://github.com/bit-mips/bitmips_experiments](https://github.com/bit-mips/bitmips_experiments)。请将实验代码克隆至本地

```
git clone git@github.com:bit-mips/bitmips_experiments.git
```

MIPS 相关系列实验主要是针对**计算机系统能力培养**而制定的一系列相关实验，通过完成这些实验，逐步"进阶"，最终可以完成一个较完备的 MIPS CPU 的设计，并且可以参加[龙芯杯](http://www.nscscc.org/)比赛。同时，本文档及相关实验也适用于本校的`计算机组成原理课程设计`等课程，如有兴趣可以参考。

该系列实验的完成是一个循序渐进的过程，难度和深度逐渐增加，同时也会有相应的硬件部分和软件部分。

## 实验介绍及目录

- 实验一：跑马灯 & 数码管
    - 该实验主要目的是让读者对 Verilog 语言以及对 Vivado 工具的使用进行简单回顾，相对来说比较简单，读者需要完成一个跑马灯的设计和一个数码管显示的设计，能够通过仿真并且能够下板运行。如果对 Verilog 语言掌握的比较好了可以跳过此环节。
    - 先修理论课程：数字逻辑
    - [实验介绍](./lab1/introduction.md)
    - [跑马灯实验指导](./lab1/led.md)
    - [数码管实验指导](./lab1/num_led.md)

- 实验二：计算机组成原理系列小实验
    - 2.1 汉明校验码
    - 2.2 指令译码（MIPS 架构指令举例）
    - 2.3 并行加法器
    - 2.4 Booth 乘法
    - 2.5 加减交替除法
    - 先修理论课程：计算机组成原理

- 实验三：单周期 CPU
    - 从该实验就要接触简单的 CPU 设计了，读者需要完成一个简单的单周期 CPU 的设计，该单周期 CPU 需要支持规定的若干条简单指令，能够仿真通过测试用例，能够下板通过测试用例。
    - 先修理论课程：计算机组成原理，体系结构
    - [实验介绍](./lab3/introduction.md)
    - [单周期实验指导](./lab3/singlecycle.md)

- 实验四：多周期 CPU
    - 本实验是一个可选实验，读者可跳过直接实现流水线 CPU 的设计。多周期本身也是 CPU 设计的一种方式，设计过程相对流水线比较简单，感兴趣可以了解。
    - 先修理论课程：计算机组成原理，体系结构

- 实验五：简单流水线
    - 本实验是要求完成一个简单的流水线 CPU 的设计。完成此实验，读者应具备一个基本的经典五级流水线的设计能力。
    - 先修理论课程：计算机组成原理，体系结构
    - [实验介绍](./lab5/introduction.md)
    - [接口简介](./lab5/soc-interface.md)

- 实验六：算法小程序运行
    - 能够将数据结构或算法导论课上的一些简单算法用 C 语言实现，并使用交叉编译工具链将其编译成 MIPS CPU 可执行的文件，之后将小程序加载至自己实现的 CPU 上运行，由此了解软件是如何在硬件上工作的。
    - 先修理论课程：C 语言，数据结构，算法导论，计算机组成原理，体系结构

- 实验七：Cache 设计
    - 本实验进行一个简单的 cache 设计，能够对 cache 原理有一个认识。
    - 先修理论课程：计算机组成原理，体系结构
    - [实验介绍](./lab7/introduction.md)
    - [Cache 实验指导](./lab7/cache.md)

- 实验八：pmon 运行
    - 本实验要求能够将 pmon 软件运行至自己设计的 CPU 上。
    - 先修理论课程：C 语言，汇编与接口，计算机组成原理，体系结构

- 实验九：ucore 移植
    - 本实验要求能够将 ucore 操作系统移植至自己设计的 CPU 上。
    - 先修理论课程：C 语言，汇编与接口，数据结构，计算机组成原理，体系结构，操作系统

- 实验十：Linux 移植 [终极目标]
    - 本实验要求能够将 Linux 操作系统移植至自己设计的 CPU 上。
    - 先修理论课程：C 语言，汇编与接口，数据结构，计算机组成原理，体系结构，操作系统

<!-- 9. 实验九：完备 soc 设计
    - 本实验要求能够自己设计一个 soc 与自实现 cpu 形成一个硬件系统，不使用龙芯提供的 soc，最终还能运行起操作系统。
    - 先修理论课程： C 语言，汇编与接口，数据结构，体系结构，计算机组成原理，操作系统 -->

- 其他相关文档
    - [Vivado 下载及安装](./others/install.md)
    - [Vivado 新建工程示例](./lab1/led.md)
    - [Vivado 使用小技巧](./others/vivado_skill.md)
    - [IP 核介绍](./others/ip.md)
    - [逻辑分析仪使用]()
    - [交叉编译工具链安装使用](./others/cross_compiler.md)

## 

