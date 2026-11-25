# 一、标题练习
# 这是 `<h1>` 一级标题
## 这是`<h2>`二级标题
###### 这是`<h6>`六级标题


# 二、列表练习
## 无序列表 
使用 - + * 可自动创建无序列表
- item 1
- item 2
- item 3

* item 1
* item 2
* item 3

+ item 1
+ item 2
+ item 3

## 有序列表 
使用数字编号，1. 2....可自动排序
1. item 1
2. item 2
3. item 3

## 任务列表
[ ]表示未完成任务，[x]表示已完成任务 前方必须加- + * 1.变为列表，且[]后方必须增加一个空格
* [x] 这是已经完成的任务
* [ ] 这是没有完成的任务


# 三、添加代码练习
区域块高亮并根据语言不同例如：bash，js，python，产生语法高亮
## 终端命令
```bash
git clone https://github.com/skills/communicate-using-markdown
```

## Javascript代码
```js
var myVar = "Hello, world!";
```

## Python代码
```python
print('Hello, world!')
```

# 四、添加图片练习
## 直接插入链接来访问
- 内部链接，使用仓库内的图片，因为当前没有，所以会显示[Mona the Octocat]内的内容
- ![Mona the Octocat](https://raw.githubusercontent.com/gitcn-org/communicate-using-markdown/main/.github/steps/myrepo/original.png)

- 外部链接，直接展示外部的图片，无法控制大小
- ![Mona the Octocat](https://octodex.github.com/images/original.png)

## 使用HTML语法
- 使用HTML写法，可以控制排版和大小，更加的灵活
- alt：图片无法显示时的替代文本
- src：图片来源地址
- width / height：控制尺寸（像素）
- align：控制对齐方式（left / right）

<img alt="Mona the Octocat" src="https://octodex.github.com/images/original.png"
width="200" align="left">

