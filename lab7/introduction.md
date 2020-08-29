# Cache 设计

本实验将指导设计并实现一个简单的 2 路组相连的 Cache。

## 实验要求
- 能够对 Cache 的原理、设计与实现有一定的了解
- 能够认识到 Cache 对提高 CPU 性能的重要意义
<!-- - 能够对线路进行简单优化，了解到线路优化对提升 CPU 时钟频率的重要性 -->

## 实验内容
本实验将指导逐步完成一个简单 Cache 的实现，这个 Cache 是一个 2 路组相联的 Cache，其中会使用到 LRU 替换算法。在完成本实验之前请确保对 Cache 的原理有所了解（本实验文档不会详细介绍 Cache 的原理），本实验指导不包含代码，仅有一些讲解。同时本实验指导还会涉及到一些接口协议的介绍，主要包括 Cache 与 CPU 之间的接口协议（类 SRAM 协议），Cache 与外部环境的接口协议（AXI 协议）。

[Cache 实验指导](./cache.md)

[一个 Cache 数据块组织框架（供参考）](https://github.com/bit-mips/bitmips_experiments/tree/master/lab7/cache%20demo)

