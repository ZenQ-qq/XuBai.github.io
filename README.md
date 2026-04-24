[README.md](https://github.com/user-attachments/files/27054655/README.md)
# 序白摄影工作室 - 作品集网站

这是一个纯前端的作品集单页网站，采用简约、高级、干净的设计风格，黑白灰为主色调，少量金色点缀。支持手机和电脑访问，微信扫码即可直接打开。

---

## 目录

- [项目结构](#项目结构)
- [如何修改内容](#如何修改内容)
- [如何添加新作品](#如何添加新作品)
- [上传到 GitHub Pages](#上传到-github-pages)
- [注意事项](#注意事项)

---

## 项目结构

```
作品集网页编程/
├── index.html          # 主页面文件（包含HTML、CSS、JavaScript）
├── images/             # 图片文件夹（存放所有作品图片）
└── README.md           # 项目说明文档
```

### 文件说明

- **index.html**：网站的主文件，包含了所有的 HTML 结构、CSS 样式和 JavaScript 代码。
- **images/**：用于存放您的作品图片文件夹，建议按作品分类建立子文件夹。

---

## 如何修改内容

### 1. 修改工作室名称和口号

打开 `index.html` 文件，找到第 547-549 行：

```html
<!-- 工作室名称（一级标题） -->
<h1>序白摄影工作室</h1>
<!-- 工作室口号/简介 -->
<p class="tagline">用心定格真实</p>
```

**修改方法**：
- 将 `序白摄影工作室` 改为您想显示的工作室名称
- 将 `用心定格真实` 改为您想显示的口号/简介

### 2. 修改作品卡片

#### 2.1 修改单个作品的主图

找到作品卡片区域，每个作品的结构如下：

```html
<div class="portfolio-item">
    <div class="media-container">
        <!-- src: 作品主图的路径 -->
        <!-- alt: 作品的标题/名称 -->
        <img src="images/work1.jpg" alt="作品标题 1">
    </div>
    <div class="portfolio-info">
        <h3 class="portfolio-title">作品标题 1</h3>
    </div>
</div>
```

**修改方法**：
- `src="images/work1.jpg"` - 改为您的作品主图路径
- `alt="作品标题 1"` - 改为您的作品名称
- `作品标题 1` - 改为您的作品标题

#### 2.2 修改联系方式

找到文件底部的联系方式区域（第 600-625 行）：

```html
<div class="contact-wrapper">
    <div class="contact-item">
        <span class="contact-label">邮箱</span>
        <a href="mailto:rrrjq@qq.com" class="contact-value">rrrjq@qq.com</a>
    </div>
    <div class="contact-item">
        <span class="contact-label">QQ</span>
        <span class="contact-value">3316973250</span>
    </div>
    <div class="contact-item">
        <span class="contact-label">电话（同微信）</span>
        <a href="tel:19150733007" class="contact-value">19150733007</a>
    </div>
</div>
```

**修改方法**：
- 将 `rrrjq@qq.com` 改为您实际的邮箱地址
- 将 `3316973250` 改为您实际的QQ号码
- 将 `19150733007` 改为您实际的电话号码
- 将 `rrrjq@qq.com` 和 `19150733007` 改为您实际要显示的值

### 3. 修改版权信息

找到文件底部的版权信息部分：

```html
<p class="copyright">© 2026 序白摄影工作室. 保留所有权利.</p>
```

将 `2026` 和 `序白摄影工作室` 改为您实际的年份和工作室名称。

---

## 如何添加新作品

### 方法一：添加新的作品卡片

1. 在 HTML 文件中找到作品卡片区域（`<div class="portfolio-grid">`）

2. 复制一个现有的作品卡片代码块，粘贴到其他作品卡片之后：

```html
<div class="portfolio-item">
    <div class="media-container">
        <img src="images/您的作品主图.jpg" alt="新作品名称">
    </div>
    <div class="portfolio-info">
        <h3 class="portfolio-title">新作品名称</h3>
    </div>
</div>
```

3. 将 `images/您的作品主图.jpg` 改为您实际上传的图片路径

4. 将 `新作品名称` 改为您想显示的作品标题

### 方法二：为作品添加多张可查看的图片

当用户点击作品卡片时，可以打开大图查看更多图片。这需要修改 JavaScript 代码中的两个地方。

#### 步骤 1：在 galleryMapping 数组中添加新作品

找到 JavaScript 代码中的 `galleryMapping` 数组（约第 685 行）：

```javascript
const galleryMapping = ['work1', 'work3', 'work5'];
```

添加新的作品键名，例如添加第4个作品：

```javascript
const galleryMapping = ['work1', 'work3', 'work5', 'work7'];
```

#### 步骤 2：在 portfolioImages 对象中添加图片集合

找到 `portfolioImages` 对象（约第 692 行），添加新的图片集合：

```javascript
// 在最后一个作品后面添加新作品
'work7': [
    { src: 'images/作品7_1.jpg', alt: '新作品图片1' },
    { src: 'images/作品7_2.jpg', alt: '新作品图片2' },
    { src: 'images/作品7_3.jpg', alt: '新作品图片3' }
]
```

#### 图片文件夹管理建议

建议在 `images` 文件夹中按作品分类建立子文件夹：

```
images/
├── work1/          # 作品1的图片文件夹
│   ├── 1.jpg
│   ├── 2.jpg
│   └── 3.jpg
├── work3/          # 作品2的图片文件夹
│   ├── 1.jpg
│   └── 2.jpg
└── work5/          # 作品3的图片文件夹
    ├── 1.jpg
    └── 2.jpg
```

这样可以让您的图片管理更加清晰有序。

---

## 上传到 GitHub Pages

### 如果您已经上传到 GitHub

1. **修改代码后重新上传**：
   - 在本地修改 `index.html` 文件
   - 将修改后的 `index.html` 文件上传到 GitHub 仓库（覆盖原有文件）
   - GitHub Pages 会自动更新，稍等几分钟即可看到最新版本

2. **添加新的作品图片**：
   - 将新的图片上传到 `images` 文件夹中
   - 或在 GitHub 仓库中创建新的图片文件夹
   - 在 `index.html` 中更新图片路径

### 首次上传到 GitHub Pages（如果需要）

1. **创建 GitHub 仓库**：
   - 访问 [GitHub](https://github.com) 并登录您的账号
   - 点击右上角的 "+" 号，选择 "New repository"
   - 填写仓库名称（如 `portfolio`）
   - 选择 "Public"（公开仓库）
   - 点击 "Create repository"

2. **上传文件**：
   - 在仓库页面，点击 "uploading an existing files"
   - 将您的 `index.html` 文件和 `images` 文件夹拖入上传区域
   - 点击 "Commit changes"

3. **启用 GitHub Pages**：
   - 在仓库页面，点击 "Settings"（设置）
   - 滚动到 "GitHub Pages" 部分
   - 在 "Source" 下拉菜单中，选择 "main" 分支
   - 点击 "Save"
   - 等待 1-2 分钟，您的网站就会生成

4. **访问您的网站**：
   - 在 "GitHub Pages" 部分，您会看到您的网站网址
   - 例如：`https://您的用户名.github.io/portfolio/`
   - 在微信中打开这个链接，扫码即可访问

---

## 注意事项

### 图片要求

- **格式**：建议使用 JPG 或 PNG 格式
- **尺寸**：建议宽度不小于 1920px，以保证在大屏幕上显示清晰
- **大小**：建议每张图片不超过 1MB，以加快加载速度
- **命名**：建议使用英文或数字命名，避免使用中文和特殊字符

### 图片路径

- 所有图片路径都相对于 `index.html` 文件
- 如果图片在 `images` 文件夹中，路径应为 `images/图片文件名.jpg`
- 如果图片在 `images/work1` 子文件夹中，路径应为 `images/work1/图片文件名.jpg`
- 路径区分大小写，请确保大小写一致

### 浏览器兼容性

- 支持所有现代浏览器（Chrome、Firefox、Safari、Edge）
- 支持手机浏览器（iOS Safari、Android Chrome）

### 微信访问

- 网站支持在微信中直接打开
- 无需任何额外配置

---

## 功能说明

### 作品卡片

- 显示作品主图和标题
- 鼠标悬停时卡片会有轻微上浮效果
- 图片会有轻微放大效果

### 图片查看器

- 点击作品卡片可打开大图查看器
- 支持左右箭头切换图片
- 支持键盘操作（ESC关闭，左右箭头切换）
- 点击查看器外部可关闭

### 响应式设计

- 电脑端：作品卡片多列显示
- 手机端：作品卡片单列显示，联系方式垂直排列

---

## 技术支持

如果在使用过程中遇到任何问题，请通过以下方式联系：

- 邮箱：rrrjq@qq.com
- QQ：3316973250
- 电话（同微信）：19150733007

---

**© 2026 序白摄影工作室. 保留所有权利.**
