---
title: "Cmake常用语句"
date: 2021-07-27T09:53:54+08:00
draft: false
---

# Cmake常用语句

```cmake
#单行注释
#[[]]多行注释
#起手式
cmake_minimum_required(VERSION 2.8)
project(hello)
#c++
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")
#c
set(CMAKE_C_STANDARD 99)
#添加子目录
add_subdirectory(sub_directory_name)
#设置源码目录
set(SOURCE_FILES main.c)
#生成可执行文件
add_executable(hello main.c)
#生成库
add_library(hello func2.c)

#设置默认编译输出为debug/release
SET(CMAKE_BUILD_TYPE "Debug”)
SET(CMAKE_BUILD_TYPE "Release")
```

