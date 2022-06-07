---
layout: wiki
title: Markdown
date: 2007-01-01
updated: 2020-10-01
categories: Wiki
description: Markdown 常用语法示例。
mermaid: true
sequence: true
flow: true
mathjax: true
mindmap: true
---


### 换行
语法规范是空格+空格+回车换行  

### 超链接
**方法一：**
```
[FreeBuf](http://www.freebuf.com/)

<http://www.freebuf.com/>
```

[FreeBuf](http://www.freebuf.com/)

<http://www.freebuf.com/>
  
**方法二：**
 ```
Some text with [a link][1] and
another [link][2].

[1]: http://example.com/ "Title"
[2]: http://example.org/ "Title"
The reference section can be anywhere in the document
 ```
Some text with [a link][1] and
another [link][2].

[1]: http://example.com/ "Title"
[2]: http://example.org/ "Title"


### 列表

```
1. 有序列表项 1

2. 有序列表项 2

3. 有序列表项 3
```

1. 有序列表项 1

2. 有序列表项 2

3. 有序列表项 3

```
* 无序列表项 1

* 无序列表项 2

* 无序列表项 3
```

* 无序列表项 1

* 无序列表项 2

* 无序列表项 3

- [x] 任务列表 1
- [ ] 任务列表 2

### 强调

```
~~删除线~~

**加黑**

*斜体*
```

~~删除线~~

**加黑**

*斜体*

### 标题

```
# 一级标题
## 二级标题
### 三级标题
#### 四级标题
##### 五级标题
###### 六级标题
```

Tips: `#` 与标题中间要加空格。

### 表格

```
| HEADER1 | HEADER2 | HEADER3 | HEADER4 |
| ------- | :------ | :-----: | ------: |
| content | content | content | content |
```

| HEADER1 | HEADER2 | HEADER3 | HEADER4 |
| ------- | :------ | :-----: | ------: |
| content | content | content | content |

1. :----- 表示左对齐
2. :----: 表示中对齐
3. -----: 表示右对齐

### 代码块
代码实现方式是键盘的~键3次 （不需要按Shift）

~~~python(No Shift)   
print 'Hello, World!'  
~~~(No Shift)


```python
print 'Hello, World!'
```
      
你也可以通过键盘的~键一次实现不需要高亮的代码。

### 引用
```
> This is Quote text
>>  This is Quoted quote. 
```  
> This is Quote text
>>  This is Quoted quote.


### 图片

```
![本站favicon](/blog/favicon.ico)

或：
![图片示例]({{ site.url }}/images/wiki/example.jpg)

```

![本站favicon](/blog/favicon.ico)

### 锚点

```
* [目录](#目录)
```

* [目录](#目录)

### Emoji

:camel:
:blush:
:smile:

### Footnotes

```
This is a text with footnote[^1].

[^1]: Here is the footnote 1 definition.
上一行会出现在页尾
```

This is a text with footnote[^1].
解释会出现在页尾

[^1]: Here is the footnote 1 definition.

### mermaid

<div class="mermaid">
sequenceDiagram
    Alice-->>John: Hello John, how are you?
    John-->>Alice: Great!
</div>

### sequence

```sequence
Andrew->China: Says Hello
Note right of China: China thinks\nabout it
China-->Andrew: How are you?
Andrew->>China: I am good thanks!
```

### flowchart

```flow
st=>start: Start
e=>end
op1=>operation: My Operation
sub1=>subroutine: My Subroutine
cond=>condition: Yes
or No?
io=>inputoutput: catch something...

st->op1->cond
cond(yes)->io->e
cond(no)->sub1(right)->op1
```

### mathjax

When $$(a \ne 0)$$, there are two solutions to $$(ax^2 + bx + c = 0)$$ and they are

$$x = {-b \pm \sqrt{b^2-4ac} \over 2a}.$$

### mindmap

```mindmap
# topic
## topic2
### topic2.1
### topic2.2
## topic3
<!--Note-->
这是一个备注
<!--/Note-->
### topic3.1
### topic3.2
#### topic3.2.1
#### topic3.2.2
#### topic3.2.3
#### topic3.2.4
#### topic3.2.5
### topic3.4
### topic3.5
### topic3.6
```


### 其他参考资料
[WordPress Markdown Quick Reference](https://wordpress.com/support/markdown-quick-reference/)