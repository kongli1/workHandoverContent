
[TOC]: #

# Table of Contents
- [1 绘制流程图Flowchart](#1-绘制流程图flowchart)
    - [1.1 流程图的定义开始Graph](#11-流程图的定义开始graph)
    - [1.2 流程图的方向](#12-流程图的方向)
    - [1.3 节点](#13-节点)
    - [1.4 连线](#14-连线)
- [2序列图 sequenceDiagram](#2序列图-sequencediagram)
    - [2.1 语法-参与者](#21-语法-参与者)
    - [2.2 语法-别名](#22-语法-别名)
    - [2.3 语法-消息的类型](#23-语法-消息的类型)
    - [2.4 语法-激活](#24-语法-激活)
    - [2.5 语法-备用](#25-语法-备用)
    - [2.6 语法-循环](#26-语法-循环)
    - [2.7 语法-Alt键](#27-语法-alt键)
    - [2.8 序列图例子:](#28-序列图例子)
- [3 甘特图 ganttDiagram](#3-甘特图-ganttdiagram)
    - [3.1 语法](#31-语法)
    - [3.2 甘特图例子：](#32-甘特图例子)


## 1 绘制流程图Flowchart
markdown中使用mermaid插件来进行画图

### 1.1 流程图的定义开始Graph
关键字graph表示一个流程图的开始，同时需要指定该图的方向  
如下：一个从左到右的流程图
```mermaid
graph LR;
　　A-->B; 
```
### 1.2 流程图的方向

1. TB（top bottom）表示从上到下
2. BT（bottom top）表示从下到上
3. RL（right left）表示从右到左
4. LR（left right）表示从左到右
5. TD与TB一样表示从上到下

### 1.3 节点
大写字母表示节点，name表示它的名字，如下图：  
默认节点的A，同时表示该节点和它的名字

1. 默认节点 A
2. 文本节点 B[B name]
3. 圆角节点 C(C name)
4. 圆形节点 D((D name))
5. 非对称节点 E>Ename]
6. 菱形节点 F{F name}

```mermaid
graph TB
   A
   B[B name]
   C(C name)
   D((D name))
   E>Ename]
   F{F name}
```
### 1.4 连线
节点间的连接线有多种形状，而且可以在连接线中加入标签：  

1. 箭头连接 A1–>B1
2. 开放连接 A2---B2
3. 标签连接 A3–text—B3 或者 A3—|text|B3
4. 箭头标签连接 A4–text –>B4 或者 A4–>|text|B4
5. 虚线开放连接 A5.-B5 或者 A5-.-B5 或者 A5..-B5
6. 虚线箭头连接 A6.->B6 或者 A6-.->B6
7. 标签虚线连接 A7-.text.-B7
8. 标签虚线箭头连接 A8-.text.->B8
9. 粗线开放连接 A9===B9
10. 粗线箭头连接 A10==>B10
11. 标签粗线开放连接 A11==text===B11
12. 标签粗线箭头连接 A12==text==>B12

```mermaid
graph TB
    A1-->B1
    A2---B2
    A3--text---B3
    A4--text-->B4
    A5-.-B5
    A6-.->B6
``` 

```mermaid
graph TB
 A7-.text.-B7
 A8-.text.->B8
 A9===B9
 A10==>B10
 A11==text===B11
 A12==text==>B12

```
例子：
```mermaid
graph TB
    st(开始)-->op[操作]
    op-->co{是或者不是}
    co--no-->sub((子程序))
    sub-->op
    co--yes-->out>输出]
    out-->en(结束)

```



## 2序列图 sequenceDiagram

### 2.1 语法-参与者
描述：参与者可以隐式的定义此页上的第一个示例。可以指定参与者按出现的顺序执行以下操作

```mermaid
sequenceDiagram
    participant John
    participant Alice
    Alice->>John: Hello John, how are you?
    John-->>Alice: Great!
```

### 2.2 语法-别名
描述：参与者可以有一个方便的标识符和一个描述性的标签
```mermaid
sequenceDiagram
    participant A as Alice
    participant J as John
    A->>J: Hello John, how are you?
    J->>A: Great!
```

### 2.3 语法-消息的类型
描述：消息可以有两种显示虚线或带有虚线

| 类型  | 描述                      |
|:------|:--------------------------|
| ->    | 没有箭头的实线             |
| -->   | 没有箭头的虚线             |
| -> >  | 带箭头的实线               |
| --> > | 带箭头的虚线               |
| -x    | 实线与十字架在结束 （异步） |
| --x   | 虚线与十字架在结束 （异步） |

### 2.4 语法-激活
可以激活和停用参与者

例子：
```mermaid
sequenceDiagram
    Alice->>John: Hello John, how are you?
    activate John
    John-->>Alice: Great!
    deactivate John
```
也是一个快捷方式符号通过附加/后缀为消息箭头：+ - 
```mermaid
sequenceDiagram
    Alice->>+John: Hello John, how are you?
    John-->>-Alice: Great!
```

激活可堆叠为相同的参与者
```mermaid
sequenceDiagram
    Alice->>+John: Hello John, how are you?
    Alice->>+John: John, can you hear me?
    John-->>-Alice: Hi Alice, I can hear you!
    John-->>-Alice: I feel great!
```


### 2.5 语法-备用
它是可以来向序列图添加注释。 
请参阅下面的示例：

```mermaid
sequenceDiagram
    participant John
    Note right of John: Text in note
```

它也可以创建跨越两个参与者的备注：
```mermaid
sequenceDiagram
    Alice->John: Hello John, how are you?
    Note over Alice,John: A typical interaction
```

### 2.6 语法-循环
描述：它可以做序列图中的快速循环
```
loop Loop text
... statements ...
end
```
请参阅下面的示例：
```mermaid
sequenceDiagram
    Alice->John: Hello John, how are you?
    loop Every minute
        John-->Alice: Great!
    end
```
### 2.7 语法-Alt键
它可以表示序列图中的备用路径，这是通过如下符号：
```
alt Describing text
... statements ...
else
... statements ...
end
```
或则是可选的序列(如果没有别的)
```
opt Describing text
... statements ...
end
```

请参阅下面的示例：
```mermaid
sequenceDiagram
    Alice->>Bob: Hello Bob, how are you?
    alt is sick
        Bob->>Alice: Not so good :(
    else is well
        Bob->>Alice: Feeling fresh like a daisy
    end
    opt Extra response
        Bob->>Alice: Thanks for asking
    end
```


### 2.8 序列图例子:
```mermaid
sequenceDiagram
A->> B: Query
B->> C: Forward query
Note right of C: Thinking...
C->> B: Response
B->> A: Forward response
```



## 3 甘特图 ganttDiagram
描述：甘特图，在1896年，第一次由 Karol Adamiecki 和独立由亨利 · 甘在 1910 年，这说明项目日程。甘特图图表说明开始日期和完成日期的终端内容和项目的摘要元素。

### 3.1 语法
```
gantt
       dateFormat  YYYY-MM-DD
       title Adding GANTT diagram functionality to mermaid

       section A section
       Completed task            :done,    des1, 2014-01-06,2014-01-08
       Active task               :active,  des2, 2014-01-09, 3d
       Future task               :         des3, after des2, 5d
       Future task2              :         des4, after des3, 5d

       section Critical tasks
       Completed task in the critical line :crit, done, 2014-01-06,24h
       Implement parser and jison          :crit, done, after des1, 2d
       Create tests for parser             :crit, active, 3d
       Future task in critical line        :crit, 5d
       Create tests for renderer           :2d
       Add to mermaid                      :1d

       section Documentation
       Describe gantt syntax               :active, a1, after des1, 3d
       Add gantt diagram to demo page      :after a1  , 20h
       Add another diagram to demo page    :doc1, after a1  , 48h

       section Last section
       Describe gantt syntax               :after doc1, 3d
       Add gantt diagram to demo page      :20h
       Add another diagram to demo page    :48h

```



### 3.2 甘特图例子：
```mermaid
gantt
    title A Gantt Diagram
    dateFormat  YYYY-MM-DD
    section Section
    A task           :a1, 2014-01-01, 30d
    Another task     :after a1  , 20d
    section Another
    Task in sec      :2014-01-12  , 12d
    another task      : 24d
```



