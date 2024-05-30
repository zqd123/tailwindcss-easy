# tailwindcss 最简单的使用方式
> 从头开始使用Tailwind CSS的最简单和最快的方法是使用Tailwind CLI工具。

## 1. 安装Tailwind CSS
> 通过npm安装 tailwindcss ，并创建您的 tailwind.config.js 文件。

```bash
#安装
npm install -D tailwindcss

#创建tailwind.config.js
npx tailwindcss init
```
## 2. 配置模板路径
> 将路径添加到 tailwind.config.js 文件中的所有模板文件。
```javascript
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: ["./src/**/*.{html,js}"],
  theme: {
    extend: {},
  },
  plugins: [],
}
```
## 3. 将Tailwind指令添加到CSS中
> 将Tailwind的每个层的 @tailwind 指令添加到主CSS文件中。

**`src/input.css`**
```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```
## 4. 启动Tailwind CLI构建过程
> 运行CLI工具扫描模板文件中的类并构建CSS。
```bash
npx tailwindcss -i ./src/input.css -o ./src/output.css --watch
```

## 5. 开始在HTML中使用Tailwind
> 将编译后的CSS文件添加到 <head> 中，并开始使用Tailwind的实用程序类来设置内容的样式。
**`src/index.html`**
```html
<!doctype html>
<html>
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link href="./output.css" rel="stylesheet">
</head>
<body>
  <h1 class="text-3xl font-bold underline">
    Hello world!
  </h1>
</body>
</html>
```
## 项目目录结构
```bash
.
├── package.json
├── tailwind.config.js
└── src
    ├── input.css
    └── output.css
    └── index.html
```
## 原理
Tailwind CSS的工作原理是扫描所有HTML文件、JavaScript组件、vue文件和任何其他模板以查找类名，生成相应的样式，然后将它们写入静态CSS文件。

例如本实例，**output.css**文件最下面添加了如下内容：
```css
.text-3xl {
  font-size: 1.875rem;
  line-height: 2.25rem;
}

.font-bold {
  font-weight: 700;
}

.underline {
  text-decoration-line: underline;
}
```

## 推荐
[在vue2中使用tailwindcss（完整教程）](https://blog.csdn.net/zqd_java/article/details/136568490)