
[TOC]:#

# Table of Contents
- [1 typora和标准Markdown的不同](#1-typora和标准markdown的不同)
    - [换行](#换行)
    - [自动URL](#自动url)
- [2 目录列表(TOC)](#2-目录列表toc)
- [3 images 插入图片](#3-images-插入图片)
- [4 headers 文档标题](#4-headers-文档标题)
- [5 lists 列表](#5-lists-列表)
- [6 tables 表格](#6-tables-表格)
- [7 code Fences 插入码块](#7-code-fences-插入码块)
- [8 Diagrams 图表](#8-diagrams-图表)
- [9 强调、斜体、删除线](#9-强调斜体删除线)
- [10 插入URL链接](#10-插入url链接)
- [11 水平分割线](#11-水平分割线)
- [12 引用](#12-引用)
- [13 Mathematics 函数](#13-mathematics-函数)



# typora For Markdown语法
Typora是一个功能强大的Markdown编辑器，使用GFM风格（即大名鼎鼎的）
Typora目前支持Mac OS和Windows，Linux
Typora可以插入数学表达式，插入表情，表格，支持标准的Markdown语法，可以使用标注....，功能强大
还可以导出PDF文件和HTLM文件

## 1 typora和标准Markdown的不同

### 换行
标准MD要在一行的最后加两个空格符才表示换行，否则是不换行的。但是GFM则没有此要求。
第一行（最后无两个空格）
第二行

### 自动URL
一个小优化，如果你直接在GFM中写一个URL链接文本，那么也会自动生成URL，同时文字也显示为该链接本身。
例如，https://github.com

## 2 目录列表(TOC)
输入[TOC]然后回车，将会产生一个目录，这个目录抽取了文章的所有标题，自动更新内容



## 3 images 插入图片
我们可以通过拖拉的方式，将本地文件夹中的图片或者网络上的图片插入


## 4 headers 文档标题

## 5 lists 列表
```
- [ ] 吃饭
- [ ] 逛街
- [ ] 看电影
```

- [ ] 吃饭
- [ ] 逛街
- [ ] 看电影


## 6 tables 表格
代码的第二行指定对齐的方式，第一个式左对齐，第二个和第三个是居中，第四个是右对齐

```
|姓名|性别|毕业学校|工资|
|:---|:---:|:---:|---:|
|杨洋|男|重庆交通大学|3200|
|峰哥|男|贵州大学|5000|
|坑货|女|北京大学|2000|
```

|姓名|性别|毕业学校|工资|
|:---|:---:|:---:|---:|
|杨洋|男|重庆交通大学|3200|
|峰哥|男|贵州大学|5000|
|坑货|女|北京大学|2000|


## 7 code Fences 插入码块
使用`包裹的内容将会以代码样式显示，例如
```
使用`print()`
```


## 8 Diagrams 图表
- 语法：最主要的是添加```mermaid


## 9 强调、斜体、删除线

**强调**：使用两个*号包裹的内容将会被强调。例如
```
**使用两个*号强调内容**
```
**斜体**：用星号来包裹斜体内容

**删除线**：使用~~包裹的文本将会具有删除的样式，例如
```
~~删除线~~
```


## 10 插入URL链接
使用尖括号包裹的url将产生一个链接  
例如：<https://www.baidu.com>  
将产生 [https://www.baidu.com](https://www.baidu.com)

## 11 水平分割线
使用***或者---，然后回车，来产生水平分割线

## 12 引用
引用部分的内容只需要在行首加上>就可以了


## 13 Mathematics 函数


