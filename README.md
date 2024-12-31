# 密码计算器

这是一个基于浏览器的密码计算器，可以通过输入域名和密码，生成一个包含数字、字母和符号的矩阵，帮助用户创建更安全的密码。
理论参考：https://www.bilibili.com/video/BV1B14y1E7Ms/

## 功能简介

- 用户输入域名和主密码后，使用 SHA-256 哈希算法生成哈希值。
- 根据生成的哈希值，分别生成三个矩阵：
  - **数字矩阵**：根据哈希值映射出数字。
  - **字母矩阵**：根据哈希值映射出字母。
  - **符号矩阵**：根据哈希值映射出符号。
- 每个矩阵均为 5x5 的格子，填充至 25 个字符，用户根据自己的意愿选择想要矩阵位置的密码。
- 在浏览器端生成，无需网络交互，保证了隐私安全。

### 前端技术

- **HTML**：
  - 用于构建页面结构，包含表单、矩阵展示区域等元素。

- **CSS**：
  - 使用了原生 CSS 来进行样式设计和布局。
  - 使用了 `flexbox` 和 `grid` 布局来实现矩阵的排列。
  - 使用 `@media` 媒体查询来支持响应式设计，适应不同设备（如手机、平板和桌面）显示。

- **JavaScript**：
  - 使用 **原生 JavaScript** 来处理页面交互和逻辑实现。
  - 使用 **`crypto.subtle.digest`** API 实现 **SHA-256** 哈希算法计算。
  - 实现了将哈希值映射到数字、字母和符号字符集的转换逻辑。
  - 使用 **事件监听器** (`addEventListener`) 来处理表单提交并动态生成矩阵。

- **图标**：
  - 使用了 **Font Awesome** 图标库来为按钮添加图标（例如：生成矩阵按钮旁的随机图标）。
  - 图标用于提升用户体验，使按钮更具吸引力。

### 使用的框架与库

- **Bootstrap 5**：
  - 使用了 **Bootstrap 5** 前端框架来简化页面布局和样式设计。
  - Bootstrap 提供了响应式布局、表单样式、按钮样式等，减少了自定义样式的工作量。
  - 引入的 Bootstrap 主要帮助快速构建一个适合各种设备的页面。

### 安全性技术

- **SHA-256 哈希算法**：
  - 使用 **SHA-256** 哈希算法将域名和密码加密成不可逆的哈希值，确保密码的安全性。
  - 哈希值用于生成数字、字母和符号矩阵，避免暴露明文密码。

## 使用方法

1. 克隆或下载此项目到本地。
2. 打开 `PasswordCalculation.html` 文件，即可在浏览器中查看和使用密码矩阵生成器。
3. 输入你想要使用的域名和密码，点击“生成矩阵”按钮，生成数字、字母和符号矩阵。

## 示例

本项目演示地址：https://zhugey.github.io/PasswordCalculation/PasswordCalculation.html
1. 输入域名：`example.com`
2. 输入密码：`123456`
3. 生成三个矩阵，选择你需要的密码。
可以自己心里记住三个矩阵的特定位置组成的密码，这样只需要记住上面输入的密码，哪怕是很简单的123456，这样最后实际要输入网站的密码只有你自己知道。

## 安全性说明

- 使用 SHA-256 哈希算法保证了生成过程的不可逆性。
- 密码矩阵是在浏览器端生成的，无需网络交互，因此避免了服务器端存储和泄露密码的风险。
  
## License

该项目使用 **MIT License** 开源许可证，具体内容请查看 [LICENSE](LICENSE) 文件。
