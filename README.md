# 华为方舟编译器源代码分析 
# Ark Compiler Source Code Analysis

## 源码下载

   下载地址：<https://code.opensource.huaweicloud.com/HarmonyOS/OpenArkCompiler/home>，可以通过`Clone` or `Download`的方式下载openarkcompiler源码
   > 注：默认源码下载目录为openarkcompiler

## 源码编译

在openarkcompiler目录下执行以下命令，编译出OpenArkCompiler，默认输出路径 openarkcompiler/out/bin。

```
source build/envsetup.sh
make
```
命令说明：

- `source build/envsetup.sh` 初始化环境，将OpenArkCompiler工具链路径openarkcompiler/src/bin设置到环境变量中
- `make` 编译OpenArkCompiler的Release版本
- `make BUILD_TYPE=DEBUG` 编译OpenArkCompiler的Debug版本

## 目前开源进度

![Alt text](https://www.openarkcompiler.cn/assets/markdown/docs/img/FAQ-Q2.png)

首次开源范围是编译器 IR（ Intermediate Representation）、RC（Reference Counting）和多语言设计思想等，用于与业界、学术界沟通交流。后续将陆续开源编译器前端、后端，支持其它语言（如 JavaScript）的编译等，当前部分Java语言特性和JVM虚拟机特性的支持未包括在本次开源代码中，包括：annotation、lambda表达式、泛型等。
