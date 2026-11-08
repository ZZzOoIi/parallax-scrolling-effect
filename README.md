# 视差滚动效果

一个基于纯 CSS 实现的全屏视差滚动演示项目，包含四屏自然风景展示。

## 效果预览

滚动页面时，每屏的背景图片固定不动，前景文字内容随滚动上移，产生强烈的视差层次感。

<video width="100%" controls>
  <source src="https://raw.githubusercontent.com/ZZzOoIi/parallax-scrolling-effect/main/demo.mp4" type="video/mp4">
</video>

## 技术实现

核心原理是使用 CSS 的 `background-attachment: fixed` 属性，让背景图片相对于视口固定，不跟随元素滚动。

```css
background: url(./img/bg1.jpg) no-repeat fixed center center/cover;
```

- **no-repeat**：背景图不重复
- **fixed**：背景图相对于视口固定（实现视差的关键）
- **center center**：背景图定位在正中心
- **cover**：背景图覆盖整个元素区域

## 项目结构

```
视差滚动效果/
├── 视差滚动效果.html    # 页面结构，包含四个全屏 section
├── 视差滚动效果.css     # 样式表，视差效果核心实现
├── img/
│   ├── bg1.jpg         # 第一屏：落日夕阳
│   ├── bg2.jpg         # 第二屏：山水湖色
│   ├── bg3.jpg         # 第三屏：广阔蓝海
│   └── bg4.jpg         # 第四屏：白雪蓝天
└── README.md
```

## 页面结构

| 屏幕 | 主题 | 内容 |
|------|------|------|
| section1 | 落日夕阳 | 黄昏夕阳与诗意文案 |
| section2 | 山水湖色 | 湖光山色与自然景观 |
| section3 | 广阔蓝海 | 大海意象与文字描述 |
| section4 | 白雪蓝天 | 雪国风光与蓝白意境 |

## 关键 CSS 样式

```css
/* 通配选择器清除默认样式 */
* { margin: 0; padding: 0; box-sizing: border-box; }

/* html 和 body 占满视口 */
html, body { width: 100%; height: 100%; }

/* 每个 section 占满一屏 */
section[class^="section"] { width: 100%; height: 100%; }

/* 视差核心：背景固定 */
.section1 { background: url(./img/bg1.jpg) no-repeat fixed center center/cover; }
```

## 使用方法

1. 直接用浏览器打开 `视差滚动效果.html` 即可查看效果
2. 上下滚动鼠标滚轮体验视差效果

## 浏览器兼容性

支持所有现代浏览器（Chrome、Firefox、Safari、Edge）。

> **注意**：在移动端，部分浏览器会忽略 `background-attachment: fixed`。如需兼容移动端，可考虑使用 JavaScript 方案或添加 `-webkit-background-size` 前缀。
