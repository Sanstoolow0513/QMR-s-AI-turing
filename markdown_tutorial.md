# Markdown 使用教程

Markdown 是一种轻量级标记语言，它允许人们使用易读易写的纯文本格式编写文档，然后转换成结构化的 HTML 文档。

## 基本语法

### 标题

使用 `#` 来表示标题，共有六级标题：

# 一级标题
## 二级标题
### 三级标题
#### 四级标题
##### 五级标题
###### 六级标题

### 段落和换行

段落之间需要空一行来分隔：

这是第一个段落。

这是第二个段落。

### 强调

使用 `*` 或 `_` 来表示斜体：

*这是斜体文字*

_这也是斜体文字_

使用 `**` 或 `__` 来表示粗体：

**这是粗体文字**

__这也是粗体文字__

### 列表

无序列表使用 `*`、`+` 或 `-`：

* 项目一
* 项目二
* 项目三

有序列表使用数字加点：

1. 第一项
2. 第二项
3. 第三项

### 链接

[这是一个链接](https://www.example.com)

或者使用引用方式：

[这是一个链接][reference]

[reference]: https://www.example.com

## 图片的使用方法

插入图片使用以下语法：

![替代文字](图片地址 "可选标题")

例如：

![Markdown Logo](https://markdown-here.com/img/icon256.png "Markdown Logo")

你也可以使用相对路径引用本地图片：

![本地图片](./images/example.png)

## 代码段的使用方法

### 行内代码

使用反引号包围行内代码：`console.log('Hello World')`

### 代码块

使用三个反引号创建代码块，并可以指定语言：

```javascript
function hello() {
  console.log('Hello, World!');
}
```

```python
def hello():
    print('Hello, World!')
```

```html
<!DOCTYPE html>
<html>
<head>
    <title>示例页面</title>
</head>
<body>
    <h1>Hello, World!</h1>
</body>
</html>
```

也可以使用缩进创建代码块（4个空格或1个tab）：

    console.log('Hello World');
    console.log('Hello World');

## 引用

使用 `>` 来表示引用：

> 这是一段引用文字
> 这是引用的第二行

## 分割线

使用三个或以上的 `*`、`-` 或 `_` 来创建分割线：

---

## 表格

使用 `|` 和 `-` 来创建表格：

| 左对齐 | 居中对齐 | 右对齐 |
| :--- | :---: | ---: |
| 内容1 | 内容2 | 内容3 |
| 内容4 | 内容5 | 内容6 |

## 总结

Markdown 是一种非常实用的标记语言，适用于写文档、博客、README 文件等。掌握基本语法后，你可以快速地创建格式良好的文档。