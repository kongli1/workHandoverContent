


# markdown插件mermaid

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

TB（top bottom）表示从上到下
BT（bottom top）表示从下到上
RL（right left）表示从左到右
LR（left right）表示从右到左
TD与TB一样表示从上到下

### 1.3 节点
大写字母表示节点，name表示它的名字，如下图：  
默认节点的A，同时表示该节点和它的名字

默认节点 A  
文本节点 B[B name]  
圆角节点 C(C name)  
圆形节点 D((D name))  
非对称节点 E>Ename]  
菱形节点 F{F name}  

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

## 序列图

## 甘特图