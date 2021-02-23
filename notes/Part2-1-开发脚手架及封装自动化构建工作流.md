# 前端工程化

### 一、工程化概述

#### 1、工程化的定义和主要解决的问题

##### （1）工程化的定义

前端工程化是指遵循一定的标准和规范通过工具提高效率的一种手段。

##### （2）主要解决的问题

- 传统语音或语法的弊端
  - 想要使用ES6+新特性，但兼容有问题
  - 想要使用Less/Sass/PostCSS增强CSS的编程性，但是运行环境不能直接支持
- 无法使用模块化/组件化
  - 想要使用模块化的方式提高项目的可维护性，但运行环境不能直接支持
- 重复的机械式工作
  - 部署上线前需要手动压缩代码及资源文件
  - 部署过程需要手动上传代码到服务器
- 代码风格统一、质量保证
  - 多人协作开发，无法影响统一大家的代码风格，从仓库中pull回来的代码质量无法保证
- 依赖后端服务接口支持
  - 部分功能开发时需要等待后端服务接口提前完成
- 整体依赖后端项目

#### 2、一个项目过程中工程化的表现

一切以提高效率、降低成本、质量保证为目的的手段都属于工程化

| 项目过程  | 工程化表现                                                 |
| --------- | ---------------------------------------------------------- |
| 创建项目  | ·创建项目结构<br />·创建特定类型文件                       |
| 编码      | ·格式化代码<br />·校验代码风格<br />·编译/构建/打包        |
| 预览/测试 | ·Web Server/Mock<br />·Live Reloading/HMR<br />·Source Map |
| 提交      | ·Git Hooks<br />·Lint-staged<br />·持续集成                |
| 部署      | ·CI/CD<br />·自动发布                                      |



#### 3、工程化≠某个工具

工程化是对项目整体规划/架构，工具是实现规划/架构的手段。

![image-20210218111004325](C:\Users\hp\AppData\Roaming\Typora\typora-user-images\image-20210218111004325.png)

![image-20210218111021843](C:\Users\hp\AppData\Roaming\Typora\typora-user-images\image-20210218111021843.png)



#### 4、工程化与Node.js



### 二、脚手架工具

#### 1、脚手架工具概要

##### 脚手架的本质作用：

创建项目基础结构、提供项目规范和约定

- 相同的组织结构

- 相同的开发范式

- 相同的模块依赖
- 相同的工具配置
- 相同的基础代码

例子：

IDE创建项目的过程就是一个脚手架的工作流程

#### 2、常用的脚手架工具

- React.js项目→create-react-app
- Vue.js项目→vue-cli
- Angular项目→angular-cli

#### 3、Yeoman简介

#####   Yeoman基本使用

- 全局范围安装yo

```
$ npm install yo --global # or yarn global add yo
```

- 安装对应的generator

```
$ npm install generator-node --global # or yarn global add generator-node
```

- 通过yo运行generator

```
$ cd path/to/project-dir
$ mkdir my-module
$ yo node
```

##### Sub Generator

常规使用步骤：

1. 明确你的需求
2. 找到合适的Generator
3. 全局范围安装找到的Generator
4. 通过Yo运行对应的Generator
5. 通过命令行交互填写选项
6. 生成你所需要的项目结构

##### 自定义Generator

基于Yeoman搭建自己的脚手架

##### 创建Generator模块

Generator本质上就是一个NPM模块

##### Generator基本结构

![image-20210223183604708](C:\Users\hp\AppData\Roaming\Typora\typora-user-images\image-20210223183604708.png)

generator-<name>

根据模块创建文件

接收用户输入数据

Vue Generator案例

发布Generator

#### Plop一个小而美的脚手架工具

Plop的具体使用

- 将plop模块作为项目开发依赖安装
- 在plopfile.js文件中定义脚手架任务
- 编写用于生产特定类型文件的模板
- 通过Plop提供的CLI运行脚手架任务

#### 脚手架工作原理