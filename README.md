# 华为方舟编译器源代码分析 
###Ark Compiler Source Code Analysis

## 目的 Purpose
写这篇方舟编译器（Ark Compiler）源代码分析的目的是帮助大家更好的理解方舟编译器的内部结构和运行机制，为以后改进这款编译器提供帮助。

The Purpose of writing the ark compiler source code analysis it to help developers better understanding the architecture 
and how it works, preparing for the future improvement. 

## 源码下载 Source Code Download

   下载地址：<https://code.opensource.huaweicloud.com/HarmonyOS/OpenArkCompiler/home>，可以通过`Clone` or `Download`的方式下载openarkcompiler源码
   > 注：默认源码下载目录为openarkcompiler

 
   Download URL：<https://code.opensource.huaweicloud.com/HarmonyOS/OpenArkCompiler/home>，Use `Clone` or `Download`to get the code
   > PS：the default directory name is: openarkcompiler

   

## 源码编译 Compiling

在openarkcompiler目录下执行以下命令，编译出OpenArkCompiler，默认输出路径 openarkcompiler/out/bin。

Under `openarkcompiler` directory, compile out `OpenArkCompiler`, default output directory is
openarkcompiler/out/bin 

```
source build/envsetup.sh
make
```
命令说明：

- `source build/envsetup.sh` 初始化环境，将OpenArkCompiler工具链路径openarkcompiler/src/bin设置到环境变量中
- `make` 编译OpenArkCompiler的Release版本
- `make BUILD_TYPE=DEBUG` 编译OpenArkCompiler的Debug版本

Commands:
- `source build/envsetup.sh` Initialize environment ，put OpenArkCompiler toolchain openarkcompiler/src/bin to env variable paths. 
- `make` make release version
- `make BUILD_TYPE=DEBUG` make debug version.

## 目前开源进度 Current Open Source Status.

![Alt text](https://www.openarkcompiler.cn/assets/markdown/docs/img/FAQ-Q2.png)

首次开源范围是编译器 IR（ Intermediate Representation）、RC（Reference Counting）和多语言设计思想等，用于与业界、学术界沟通交流。
后续将陆续开源编译器前端、后端，支持其它语言（如 JavaScript）的编译等，当前部分Java语言特性和JVM虚拟机特性的支持未包括在本次开源代码中，
包括：annotation、lambda表达式、泛型等。

The initial open source range of ark compiler is the Intermediate Representation (IR), Reference Counting(RC) and multi
language design principles, used for communicating with industry. The following open source plan includes 
frontend, backend, multi-lang support(Ex. Javascript) etc. Current open sourced parts do not contain some Java and JVM 
specific features, like annotation, lambda expression, generics etc.
