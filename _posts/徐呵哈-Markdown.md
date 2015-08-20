title: 徐呵哈_Markdown
categories: [Markdown]
tags: [Markdown,Archives]
date: 2015-06-09 20:21:23
---
#写前
这是一份关于Markdown的整理使用文档  
一般词法符号和文本之间都要隔一个空格  
所有符号都在英文状态下
<!--more-->
#正文
##<a name='index'/>目录
* [标题](#title)
* [横线](#line)
* [文本](#text)
##<a name='title'/>标题
文本前加上`#`即可，一至六个`#`对应一至六级标题  
示例：  
  
	# 一级标题  
	##二级标题  
	###三级标题  
	####四级标题  
	#####五级标题  
	######六级标题  
效果：  
# 一级标题  
##二级标题  
###三级标题  
####四级标题  
#####五级标题  
######六级标题
注意：`#` 和 一级标题之间建议保留一个字符的空格（标准写法）  
##字体
###粗体
规则：`** + 文本 + **`
示例：  
	**加粗文字**
效果：  
**加粗文字**
###斜体
规则：`* + 文本 + *`
示例：  
	*斜体文字*
效果：  
*斜体文字*
##<a name='line'/>横线
示例：  
  
	***  
	---  
	___  
效果：  
***
---
___
##<a name='text'/>文本
###普通文本
示例：  

	这是一段普通文本  
效果：  
这是一段普通文本
###换行
在一段文本后加两个空格然后回车即可换行，或者两次回车也可换行  
示例：  

	文本后加两个空格然后回车  
	即可换行  
效果：  

文本后加两个空格然后回车  
即可换行
###单行文本
示例：

	Hello,大家好，我是果冻虾仁。
	哎哟，不
##列表
在文字前加上`-`即可  
示例：

	- 列表一  
	- 列表二  
	- 列表三
效果：  

- 列表一  
- 列表二  
- 列表三  

注意：在`-`符号和文字之间必须要有一个空格，结束列表后需要敲两次回车  
如果希望有序列表，则使用`1`、`2`、`3`+空格+文字  
示例：  

	1. 列表一
	2. 列表二
	3. 列表三  

效果：  

1. 列表一
2. 列表二
3. 列表三
##链接
规则：[显示文本](链接地址)  
示例：  

	[徐呵哈](http://www.inets.wang/blog)
效果：  
[徐呵哈](http://www.inets.wang/blog)
##图片
规则：![](图片链接地址)  
示例：  

	![](http://ww4.sinaimg.cn/bmiddle/aa397b7fjw1dzplsgpdw5j.jpg)
效果：  
![](http://ww4.sinaimg.cn/bmiddle/aa397b7fjw1dzplsgpdw5j.jpg)  
注意：插入图片的语法和链接的语法很像，只是多了一个`!`符号
##引用
规则：>+被引用的文字  
示例：

	> 一盏灯， 一片昏黄； 一简书， 一杯淡茶。 守着那一份淡定， 品读属于自己的寂寞。 保持淡定， 才能欣赏到最美丽的风景！ 保持淡定， 人生从此不再寂寞。
效果：  
> 一盏灯， 一片昏黄； 一简书， 一杯淡茶。 守着那一份淡定， 品读属于自己的寂寞。 保持淡定， 才能欣赏到最美丽的风景！ 保持淡定， 人生从此不再寂寞。  

注意：退出时可以敲两个回车
##表格
| ABCD | EFGH | IJKL |
| -----|:----:| ----:|
| a    | b    | c    |
| d    | e    |  f   |
| g    | h    |   i  |

### 高效绘制 [流程图](https://www.zybuluo.com/mdeditor?url=https://www.zybuluo.com/static/editor/md-help.markdown#7-流程图)

```flow
st=>start: Start
op=>operation: Your Operation
cond=>condition: Yes or No?
e=>end

st->op->cond
cond(yes)->e
cond(no)->op
```

### 高效绘制 [序列图](https://www.zybuluo.com/mdeditor?url=https://www.zybuluo.com/static/editor/md-help.markdown#8-序列图)

```seq
Alice->Bob: Hello Bob, how are you?
Note right of Bob: Bob thinks
Bob-->Alice: I am good thanks!
```
