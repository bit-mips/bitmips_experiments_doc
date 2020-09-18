# 流水线 CPU SOC 接口规范

### 整体架构
本实验整个项目工程的架构图如下：

![](./img/../../img/lab3/p1.png)

其中，做实验时只需要完成 myCPU 部分的代码即可，其他部分代码已补充完毕。在实现 myCPU 时需要将其最终的对外接口符合下面的接口定义。

**关于数据存取：**

MIPS 架构是一个统一编址的指令集架构，即没有 `IN`、 `OUT` 这类访问外设的指令。MIPS 架构是将地址空间中的一部分地址分配给 I/O 端口，这样在访问外设时跟访问数据存储器是相同的操作，即都是使用 LW、LW 这类访存指令来访问，因此读写外设和数据存储器是没有区别的。

因而上述架构图中会有一个 `bridge` 模块，该模块是用来确定读写的是数据存储器还是外设。该模块的工作原理就是通过地址来区分，本实验中，设定外设的地址空间是 **`0xbfaf_0000 ~ 0xbfaf_ffff`**，因此，当访存指令给出的访问地址是在该范围内时即说明要访问外设，`bridge` 会控制外设读写而不是数据存储器，反之亦然。 


### 接口定义

myCPU 模块对外接口如下：

| 信号              | 方向   | 位宽 | 含义                                           |
| -                 | -      | -    | -                                              |
| resetn            | input  | 1    | 复位信号（低使能）                             |
| clk               | input  | 1    | 时钟信号                                       |
| int               | input  | 6    | 中断信号（高使能，本实验中可以忽略）           |
|                   |        |      |                                                |
| inst_sram_en      | output | 1    | 指令通道使能                                   |
| inst_sram_wen     | output | 1    | 是否写数据（总为 0）                           |
| inst_sram_addr    | output | 32   | 指令地址                                       |
| inst_sram_wdata   | output | 32   | 写入的数据（不需要）                           |
| inst_sram_rdata   | input  | 32   | 读取的指令                                     |
|                   |        |      |                                                |
| data_sram_en      | output | 1    | 数据通道使能                                   |
| data_sram_wen     | output | 1    | 是否写数据                                     |
| data_sram_addr    | output | 32   | 数据地址                                       |
| data_sram_wdata   | input  | 32   | 写入的数据（只有 data_sram_wen 为 1 时有意义） |
| data_sram_rdata   | output | 32   | 读取的数据                                     |
|                   |        |      |                                                |
| debug_wb_pc       | output | 32   | 不需要                                         |
| debug_wb_rf_wen   | output | 32   | 不需要                                         |
| debug_wb_rf_wnum  | output | 32   | 不需要                                         |
| debug_wb_rf_wdata | output | 32   | 不需要                                         |

控制信号主要为 `rst` 和 `clk` 信号，其中一个提供低使能的复位信号，一个提供时钟信号以同步 CPU。

在取指这一部分有三个主要信号，`inst_sram_en` 作为使能，控制 sram 是否读取指令。 `inst_sram_addr` 提供当前需要取出的指令的地址，这是一个 32 位的地址，而 `inst_sram_rdata` 是**有一周期延迟**下取回的指令数据，也是 32 位（MIPS 指令是定长指令，都是 32 位）。

在访存部分有如下几个信号，`data_sram_en` 作为使能，控制 sram 是否读取或写入数据。 `data_sram_addr` 提供访存的地址，加载和存储指令复用该信号作为访存地址。`data_sram_wdata` 提供存储指令将要存储的数据，当访存指令为加载指令时该信号不起作用。`data_sram_wen` 在访存指令为存储指令时置高电平，表示将写存储器，其他情况置低电平。`data_sram_rdata` 是访存指令为加载指令时**延迟一个周期**返回的一个加载数据，即 LW 等指令从存储器中读取到的数据。

下图展示了 LUI, LW, SW 对接口使用情况的波形图。

![](../img/lab5/wavedrom-svgcontent.svg)
