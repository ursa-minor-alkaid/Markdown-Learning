# 使用html及css

时间：`2025年10月12日`

此外，还可以使用html和css实现markdown不支持的内容

## 基本介绍

- 许多 Markdown 渲染器其实是先将 Markdown 文本转换成 html，然后再交由浏览器或预览工具显示的，所以可以直接写 html 代码
- 推荐的使用 CSS 的方式
  - 内联样式
  - 外部样式表 
  - 最好不要使用内部样式表

---

## 内联样式基础语法

### 1. \<span> 标签

- 行内元素
- 语法：`<span style="属性:值（声明1）; 属性:值（声明2）;">内容</span>`；常用属性见下
  - `font-size`
  - `font-family`
  - `color`
  - `border` & `border-radius`
  - `padding` & `margin`
- 可以和 **加粗** 、*斜体* 一起使用
- 示例：
  - <span style="font-size:24px; color:#0f78ff;">变大并变成蓝色</span>
  - <span style="font-size:12px; font-family:cambria;">*hello*</span>
  - <span style="font-size:30px; font-family:cambria; padding:7px; border:2.5px solid grey; border-radius: 30px;">**world!**</span>

### 2. \<div> 标签

- 块级元素

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

