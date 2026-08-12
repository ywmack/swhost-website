# SwHosts 产品信息

---

## 一、基础信息

| 项目 | 内容 |
|------|------|
| 软件名称 | SwHosts |
| Slogan | 一站式 HOSTS 管理与反向代理工具，让本地开发调试更高效 |
| 版本号 | v0.1.4 |
| 更新日期 | 2026-08-12 |
| 软件类型 | 桌面 GUI 程序 |
| 项目状态 | Beta 测试版 |
| 项目主页 | https://ywmack.github.io/swhost-website/ |
| 下载地址 | https://github.com/ywmack/swhost-website/releases |

---

## 二、软件简介

SwHosts 是一款面向开发者的桌面工具，将 **HOSTS 文件管理** 和 **HTTP 反向代理** 整合到一个应用中。

**解决的痛点：**
- 手动编辑 `/etc/hosts` 切换环境效率低、容易出错
- 反向代理需要额外装 Nginx/Caddy，配置复杂
- HOSTS 管理 + 代理 + DNS 刷新需要多个工具配合
- 端口被占用时排查困难

**目标用户：** 前端/后端开发者、全栈工程师、运维人员、测试人员

---

## 三、核心功能

### 🌟 主打功能

**1. HOSTS 方案管理**
- 创建多个 HOSTS 方案（本地编辑 / 远程 URL 拉取）
- 一键激活/停用，自动写入系统 HOSTS 文件
- 拖拽排序、文件夹分组
- 远程方案支持定时自动刷新

**2. HTTP 反向代理**
- 内置 HTTP（80）和 HTTPS（443）反向代理
- 多条代理规则，每条可独立启用/停用
- 代理访问日志实时查看
- 端口占用检测，显示占用进程名和 PID

**3. HOSTS 编辑器**
- 内置代码编辑器，行级颜色标识（绿色=正确、红色=有误、灰色=注释）
- 快捷键 `Cmd/Ctrl + /` 快速注释
- 自动保存，修改后即时生效

### 🔧 辅助功能

- **全局搜索**：搜索所有方案中的域名、IP，模糊匹配
- **DNS 自动刷新**：修改 HOSTS 后自动刷新系统 DNS 缓存
- **系统 HOSTS 查看**：查看和一键重置系统 HOSTS
- **操作历史**：记录所有修改，支持回滚
- **端口检测**：检测 80/443 端口占用，显示进程详情

---

## 四、技术信息

### 技术栈
- **后端**：Go 1.25+
- **前端**：Vue 3 + TypeScript + Pinia
- **框架**：[Wails v2](https://wails.io/)（Go + WebView 桌面应用框架）
- **编辑器**：CodeMirror 6
- **样式**：Tailwind CSS

### 支持系统

| 操作系统 | 架构 |
|---------|------|
| macOS 12+ | Apple Silicon (arm64) / Intel (amd64) |
| Windows 10+ | x64 |

- 无需额外依赖，独立可执行文件
- 修改 HOSTS 需管理员权限

### 数据存储
- macOS: `~/Library/Application Support/SwHosts/config.json`
- Windows: `%APPDATA%/SwHosts/config.json`

---

## 五、快速上手

### 安装
- **macOS**：下载 `.dmg`，拖入应用程序
- **Windows**：下载 `.exe`，运行安装

### 使用步骤
1. 启动 SwHosts
2. 创建 HOSTS 方案（本地编辑或远程 URL）
3. 点击开关激活方案
4. 首次使用输入管理员密码授权
5. HOSTS 立即生效

### 代理配置
1. 在「代理」面板添加规则：来源域名 → 目标地址
2. 开启 HTTP 代理开关
3. 确保 HOSTS 中已添加对应域名记录
4. 访问域名即可自动代理

---

## 六、下载

| 平台 | 下载链接 |
|------|---------|
| macOS (Apple Silicon) | [SwHosts-macos-arm64.dmg](https://github.com/ywmack/swhost-website/releases) |
| macOS (Intel) | [SwHosts-macos-amd64.dmg](https://github.com/ywmack/swhost-website/releases) |
| Windows (x64) | [SwHosts-windows-amd64.exe](https://github.com/ywmack/swhost-website/releases) |

---

## 七、版权 & 免责声明

- **开源协议**：MIT License

> 本软件仅供学习和研究使用。使用本软件修改系统 HOSTS 文件所产生的任何后果由用户自行承担。作者不对因使用本软件导致的系统故障、数据丢失或其他损害负责。

---

## 八、FAQ

**Q: 为什么需要管理员权限？**
A: 修改系统 HOSTS 文件需要管理员权限，这是操作系统的安全限制。

**Q: 代理端口被占用怎么办？**
A: SwHosts 会检测端口占用并显示占用进程。如果是本程序已在运行，无需处理；如果是其他程序，请先停止该程序或在设置中修改代理端口。

**Q: 关闭应用后 HOSTS 会恢复吗？**
A: 不会。HOSTS 修改是持久的，关闭应用后仍然生效。如需恢复，请手动编辑或切换到其他方案覆盖。

**Q: 如何备份配置？**
A: 复制配置文件即可：macOS 位于 `~/Library/Application Support/SwHosts/config.json`，Windows 位于 `%APPDATA%/SwHosts/config.json`。

---

## 九、更新日志

### v0.1.4 (2026-08-12)
- ✨ 代理开关添加「启动中/停用中」过渡状态
- ✨ 代理访问日志功能
- ✨ 代理规则启用/停用开关
- ✨ 端口占用检测显示占用进程详情
- ✨ HOSTS 内容搜索功能
- ✨ HOSTS 编辑器注释快捷键
- ✨ 代理规则输入优化

---

## 十、素材清单

| 素材 | 路径 |
|------|------|
| 应用图标 | `frontend/src/assets/images/app-icon.png` |
| Logo | `frontend/src/assets/images/logo-universal.png` |
| 应用截图 | `docs/images/app-screenshot.png` |



