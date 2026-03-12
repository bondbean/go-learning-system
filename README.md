# 围棋学习激励系统部署指南

本指南将帮助您在其他电脑上部署和使用围棋学习激励系统。

## 方法一：直接使用HTML文件（最简单）

1. **复制文件**：
   - 将 `index.html` 文件复制到U盘或通过邮件发送给其他电脑
   - 也可以将整个 `go_learning_system` 文件夹复制过去

2. **打开使用**：
   - 在目标电脑上，直接双击 `index.html` 文件
   - 系统会自动用默认浏览器打开网站
   - 无需安装任何额外软件

## 方法二：本地服务器部署（推荐）

使用本地服务器可以获得更好的体验，特别是在处理本地存储数据时。

### 使用Python内置服务器（推荐）

1. **确保目标电脑已安装Python**：
   - Windows：从官网下载安装 Python 3.6+
   - Mac/Linux：系统通常已预装Python

2. **启动本地服务器**：
   - 在 `go_learning_system` 文件夹中打开命令提示符/终端
   - 运行以下命令：
     ```bash
     # Python 3
     python -m http.server 8000
     
     # 或 Python 2
     python -m SimpleHTTPServer 8000
     ```

3. **访问网站**：
   - 打开浏览器，访问 `http://localhost:8000`
   - 或访问 `http://127.0.0.1:8000`

### 使用Node.js的http-server

1. **安装Node.js和npm**：
   - 从官网下载并安装 Node.js

2. **安装http-server**：
   ```bash
   npm install -g http-server
   ```

3. **启动服务器**：
   ```bash
   cd go_learning_system
   http-server -p 8000
   ```

## 方法三：局域网分享

如果您想在同一网络下的多台电脑上使用：

1. **获取本机IP地址**：
   - Windows：在命令提示符中运行 `ipconfig`
   - Mac/Linux：在终端中运行 `ifconfig` 或 `ip addr`

2. **启动本地服务器**（参考方法二）

3. **其他电脑访问**：
   - 在同一网络的其他电脑上，打开浏览器
   - 访问 `http://您的IP地址:8000`
   - 例如：`http://192.168.1.100:8000`

## 方法四：云服务部署（永久在线）

如果您想让系统永久在线，可以部署到云服务：

### GitHub Pages（免费）

1. **创建GitHub账号**：
   - 访问 GitHub官网 注册账号

2. **创建新仓库**：
   - 点击 "New repository"
   - 仓库名建议使用 `go-learning-system`

3. **上传文件**：
   - 可以使用Git命令行或GitHub Desktop上传文件
   - 也可以直接在GitHub网页上上传文件

4. **启用GitHub Pages**：
   - 进入仓库设置
   - 找到 "GitHub Pages" 部分
   - 选择 "main" 分支，点击 "Save"
   - 几分钟后，系统会提供一个URL供您访问

### Netlify（免费）

1. **创建Netlify账号**：
   - 访问 Netlify官网 注册账号

2. **拖拽部署**：
   - 登录后，直接拖拽 `go_learning_system` 文件夹到Netlify界面
   - 系统会自动部署并提供一个URL

## 数据存储说明

本系统使用浏览器的localStorage存储数据：

- **本地使用**：数据存储在当前浏览器中
- **多设备同步**：如需在多设备间同步数据，需要手动导出/导入localStorage数据
- **数据备份**：建议定期备份localStorage数据

## 浏览器兼容性

系统支持所有现代浏览器：
- Chrome 60+
- Firefox 55+
- Safari 12+
- Edge 79+

## 登录信息

系统默认登录凭证：
- **用户名**：nlxq
- **密码**：6688

## 常见问题

### Q: 为什么数据在不同浏览器间不共享？
A: localStorage是按浏览器存储的，换浏览器或清除缓存会导致数据丢失。

### Q: 如何备份我的数据？
A: 在浏览器控制台（F12 > Console）中运行：
```javascript
localStorage.getItem('goLearningSystem')
```
然后复制输出的字符串进行备份。

### Q: 如何恢复备份的数据？
A: 在浏览器控制台中运行：
```javascript
localStorage.setItem('goLearningSystem', '备份的字符串')
```

### Q: 网站无法访问怎么办？
A: 检查本地服务器是否在运行，端口是否正确，防火墙是否阻止了访问。