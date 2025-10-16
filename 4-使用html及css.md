# 使用html及css

时间：`2025年10月12日`

此外，还可以使用html和css实现markdown不支持的内容

## 基本介绍

- 许多 Markdown 渲染器其实是先将 Markdown 文本转换成 html，然后再交由浏览器或预览工具显示的，所以可以直接写 html 代码
- 使用 CSS 的方式：内联样式
  - 最好不要使用内部样式表
- **注意事项**：
  - html 和 css 语法到底能否被支持，最后还是取决于使用的平台的渲染器
  - html 和 css 的语法能实现很多功能，但不要用它来写整个文档。它的作用是弥补 Markdown 的不足。**如果你的文档变得充满了这二者，也许你该考虑直接使用 html 来写这个页面了**。
  - 要写标签本身的时候，记得使用代码块或者使用 `\` 转义

---

## 内联样式基础语法

### 1. \<span> 标签

- 行内元素
- 语法：`<span style="属性:值（声明1）; 属性:值（声明2）;">内容</span>`；常用的 **`style`属性** 见下
  - `font-size`
  - `font-family`
  - `color`
  - `background-color`
  - `border` & `border-radius`
  - `padding` & `margin`
- 可以和 **加粗** 、*斜体* 一起使用
- 示例：
  - <span style="font-size:24px; color:#0f78ff;">变大并变成蓝色</span>
  - <span style="font-size:12px; font-family:cambria;">*hello*</span>
  - <span style="font-size:30px; font-family:cambria; padding:7px; border:2.5px solid grey; border-radius: 30px;">**world!**</span>

---

### 2. \<div> 标签

- 块级元素：“Division”，看作一个盒子
- 语法：同上
  - `align`：不是 `style`
  - `style` 的 `display`
- **示例一**：自定义信息提示框的效果
  - Markdown 的 `>` 引用块样式很单一。我们可以用 \<div> 创建更醒目的、带有特定颜色和图标的提示框。
  - 可以通过改变颜色，创建别的类型的信息框，如警告 (orange)、危险 (red) 等

<div style="background-color: #e7f3fe; border-left: 6px solid #2196F3; padding: 15px; margin-bottom: 20px;">
  
  <a id="information"> **ℹ️ 信息** </a>
  
这是一个信息提示框。你可以用它来突出显示重要提示或补充说明。注意 `<div>` 标签和内部的 Markdown 内容之间需要有**空行**。
  
- 列表项一
- 列表项二
  
</div>

- **示例二**：控制图片大小和对齐方式
  - Markdown 原生语法 `![alt](src)` 无法方便地控制图片的大小和对齐。用 \<div> 包裹 \<img> 标签是完美的解决方案。

<div align="center" style="margin: 20px 0;">
  <img src="./images/4-1-Align_test.png" alt="Align_test" style="max-width: 50%; height: auto;">
</div>

---

### 3. \<details> 和 \<summary>

- 用于创建可折叠内容
- 语法：`<details>` 包裹的内容，除了 `<summary>` 会被显示，其他都会被折叠
- 示例：

    <details style="border:2px solid #0f7811; padding:10px; border-radius:25px; background-color:#0f78;">
        <summary>点击查看详情</summary>

        以下为折叠内容：

        style="border:2px solid #0f7811; padding:10px; border-radius:25px; background-color:#0f78;

    </details>

---

### 4. 其他常用标签

1. **\<kbd>**（keyboard）：用于表示用户从键盘输入的内容
   1. 在编写技术文档、教程或操作指南时，用来清晰地指示需要用户按下的按键。多数平台会为其渲染一个独特的 **“按键”样式**。
   2. 示例：要复制文本，请按 <kbd>Ctrl</kbd> + <kbd>C</kbd>。
2. **\<a>**（anchor）：
   1. 创建页面内部的跳转链接（即，锚点）
   2. 在长篇文章中创建目录，让读者可以快速跳转到指定章节。这是一个 Markdown 链接无法直接实现的功能（md只能实现转跳到标题）。
   3. 语法：在目标位置设置一个 `id`: `<a id="id-01"> Content </a>`，在需要点击跳转的地方创建一个链接：`[转跳的文字](#id)`
   4. 示例：转跳到[\<div>的示例](#information)
3. **\<p>**（paragraph）：
   1. Markdown 中空一行就是段落，但显式使用 \<p> 标签可以让你更精确地控制单个段落的对齐方式
4. **\<hr>**（horizontal rule，水平尺）：
   1. Markdown 中可以用 `---` 或 `***` 创建分割线，但使用 \<hr> 标签可以让你通过 style 属性自定义分割线的样式
   2. 注意使用的属性是 `height` 和 `background-image`
   3. 示例：<hr style="height: 5px; background-image: linear-gradient(to right, red, yellow, blue);">
5. **\<br>**（break）：强制换行
6. **\<mark>**：高亮
   1. 可以通过修改参数来改变高亮的字体颜色及背景颜色
   2.  `<mark style="color:目标字体颜色; background-color:目标高亮颜色;"></mark>`；
   3.  例如
       1.  <mark style="background-color: lightblue;">淡蓝色</mark>
       2.  <mark style="background-color: #333; color: #fef08a;">突出强调</mark>
7. **\<ul>**（unordered list）, **\<ol>**（ordered list）, **\<li>**（list item）：略，比起markdown自带的列表，其可以实现更精细的对列表的控制
