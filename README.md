# xtensa-tool-chain

## 介绍

工具链是用于编译代码和构建应用程序的一组程序。安装预构建的工具链可以更快捷的开发ESP32、ESP8266

**仓库内所含工具链仅支持Linux环境**

## 安装先决条件

To compile with ESP-IDF you need to get the following packages:

- CentOS 7:

  ```
  sudo yum install gcc git wget make ncurses-devel flex bison gperf python python2-cryptography
  ```

- Ubuntu and Debian:

  ```
  sudo apt-get install gcc git wget make libncurses-dev flex bison gperf python python-pip python-setuptools python-serial python-cryptography python-future python-pyparsing python-pyelftools libffi-dev libssl-dev
  ```

- Arch:

  ```
  sudo pacman -S --needed gcc git make ncurses flex bison gperf python-pyserial python-cryptography python-future python-pyparsing python-pyelftools
  ```

## 工具链设置

1.下载相应工具链并将其解压缩

2.更新文件中的`PATH`环境变量`~/.profile`。要使`xtensa-esp32-elf`所有终端会话都可用，请在`~/.profile`文件中添加以下行：

```
export PATH="$HOME/esp/xtensa-esp32-elf/bin:$PATH"
```

或者，您可以为上述命令创建别名。这样，您仅在需要时才能获得工具链。为此，请在`~/.profile`文件中添加另一行：

```
alias get_esp32='export PATH="$HOME/esp/xtensa-esp32-elf/bin:$PATH"'
```

然后，当您需要工具链时，可以`get_esp32`在命令行上键入，该工具链将添加到您的`PATH`。

## 注意

从ESP-IDF V4.0开始，默认的构建系统基于CMake。通过install.sh以及export.sh两个脚本文件便可自动下载相应工具链并添加路径至PATH。

