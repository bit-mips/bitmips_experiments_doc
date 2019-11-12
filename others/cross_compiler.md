# 交叉编译工具链安装及使用

## 安装步骤

1. 首先主机需要有 Linux 环境，可以是双系统也可以是虚拟机。Linux 环境建议使用 Ubuntu16.04，目前来说在 Ubuntu16.04 下使用还没有出现较大的问题，网上有些博客说 Ubuntu18.04 可能会有问题。
    - 注：不要使用 wsl，要安装的交叉编译工具链是32位程序，而 wsl 目前只支持运行64位程序。

2. 在 linux 命令行下，然后使用如下命令下载
    ```
    wget http://ftp.loongnix.org/toolchain/gcc/release/gcc-4.3-ls232.tar.gz
    ```

3. 解压
    ```
    sudo tar –zxvf gcc-4.3-ls232.tar.gz -C /
    ```

4. 设置环境变量 PATH
    ```
    echo "export PATH=/opt/gcc-4.3-ls232/bin:$PATH" >> ~/.bashrc
    source ~/.bashrc
    ```

如果机器是64位的机器还需执行如下命令
```
sudo apt-get install lsb-core 
```

完成上述工作后，可以输入 `mipsel-linux-gcc -v`，如果可以看到有版本号输出，说明配置正确。

## 使用

使用方式同 gcc，可以结合 coe 工具使用。
