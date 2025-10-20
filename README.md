# KubeSpeed

<div align="center">

![KubeSpeed Logo](KubeSpeed/Assets/avalonia-logo.ico)

**现代化的 Kubernetes 集群管理工具**

基于 .NET 9 和 Avalonia UI 构建，为开发者和运维人员提供直观、高效的 K8s 资源管理体验

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE.txt)
[![.NET](https://img.shields.io/badge/.NET-9.0-purple.svg)](https://dotnet.microsoft.com/)
[![Platform](https://img.shields.io/badge/platform-Windows-lightgrey.svg)](https://github.com/dotnet/core/blob/main/release-notes/9.0/supported-os.md)

</div>

## ✨ 核心功能

### 🔧 集群管理
- **多集群支持** - 同时管理多个 Kubernetes 集群
- **上下文切换** - 快速切换不同的 K8s 上下文
- **集群连接** - 支持本地和远程集群连接
- **实时状态监控** - 集群健康状态实时显示

### 📊 资源管理
- **资源浏览器** - 树形结构浏览所有 K8s 资源
- **命名空间管理** - 全局命名空间列表和切换
- **资源详情查看** - 支持 YAML 格式查看和编辑
- **实时事件监听** - 资源变更事件实时更新

### 🐳 Pod 管理
- **Pod 概览** - 详细的 Pod 状态和资源使用情况
- **容器详情** - 容器资源使用、探针状态等信息
- **日志查看** - 实时 Pod 日志流查看
- **终端访问** - 直接在应用内执行 Pod 命令
- **文件浏览** - 浏览和查看 Pod 内文件系统

### 📦 Helm 集成
- **Helm Chart 管理** - 本地和远程 Chart 安装
- **ArtifactHub 集成** - 直接从 ArtifactHub 搜索和安装 Chart
- **应用管理** - 已安装应用的管理和升级

### 🎨 用户体验
- **现代化 UI** - 基于 Semi Design 的美观界面
- **中文本地化** - 完整的中文界面支持
- **主题支持** - 明暗主题切换
- **响应式设计** - 适配不同屏幕尺寸

## 🛠️ 技术特性

### 架构设计
- **.NET 9** - 基于最新 .NET 框架
- **Avalonia UI** - 跨平台桌面应用框架
- **MVVM 架构** - 清晰的代码结构和数据绑定
- **依赖注入** - 模块化的服务架构

### 性能优化
- **异步操作** - 所有 K8s API 调用均为异步
- **实时更新** - WebSocket 连接实现实时数据更新
- **内存优化** - 高效的资源管理和缓存机制

## 📋 系统要求

- **操作系统**: Windows 10/11 (x64)
- **运行时**: 自包含 .NET 9 运行时（无需额外安装）
- **内存**: 建议 4GB 以上
- **磁盘空间**: 约 150MB

## 📦 安装方式

### 方式一：MSI 安装包（推荐）
1. 从 [Releases](../../releases) 页面下载 `KubeSpeed-Setup-x64.msi`
2. 双击运行安装程序
3. 按照向导完成安装
4. 从开始菜单或桌面快捷方式启动应用

### 方式二：便携版
1. 从 [Releases](../../releases) 页面下载 `KubeSpeed-Portable-x64.zip`
2. 解压到任意目录
3. 运行 `KubeSpeed.Desktop.exe`

## 🚀 快速开始

### 前置条件
确保你的系统已安装并配置：
- `kubectl` 命令行工具
- 有效的 `kubeconfig` 文件

### 使用步骤
1. 启动 KubeSpeed 应用
2. 在集群管理界面选择要连接的 K8s 集群
3. 等待连接建立和资源加载完成
4. 开始管理你的 Kubernetes 资源！

## 🏗️ 项目结构

```
KubeSpeed/
├── KubeSpeed/                 # 主应用程序
├── KubeSpeed.Core/           # 核心 UI 组件
├── KubeSpeed.Features/       # 功能模块
├── KubeSpeed.Services/       # K8s 服务层
├── KubeSpeed.Common/         # 公共组件
├── KubeSpeed.Repository/     # 数据仓库层
├── KubeSpeed.Resource/       # 资源文件
├── KubeSpeed.Desktop/        # 桌面应用入口
├── KubeSpeed.Browser/        # Web 版本（开发中）
├── KubeSpeed.Android/        # Android 版本（计划中）
├── KubeSpeed.iOS/           # iOS 版本（计划中）
└── KubeSpeed.Installer/     # 安装包项目
```

## 🔧 开发环境

### 环境要求
- Visual Studio 2022 或 JetBrains Rider
- .NET 9 SDK
- Git

### 构建步骤
```bash
# 克隆仓库
git clone <repository-url>
cd KubeSpeed

# 还原依赖
dotnet restore

# 构建项目
dotnet build

# 运行桌面版
dotnet run --project KubeSpeed.Desktop
```

### 打包发布
```bash
# 构建 Release 版本
dotnet publish KubeSpeed.Desktop\KubeSpeed.Desktop.csproj -c Release -r win-x64 --self-contained true -p:PublishSingleFile=true

# 构建 MSI 安装包（需要 WiX Toolset）
.\build-msi-x64.bat

# 构建便携版
.\build-portable.ps1
```

## 🔒 安全特性

- **代码混淆** - Release 版本包含代码混淆保护
- **数字签名** - 安装包经过数字签名验证
- **本地存储** - 敏感配置信息本地加密存储

## 🐛 已知问题

- 某些复杂的 CRD 资源可能显示不完整
- 大型集群初次加载可能需要较长时间
- 目前仅支持 Windows 平台

## 🔄 后续计划

- [ ] 支持更多平台（macOS、Linux）
- [ ] 增加资源编辑功能
- [ ] 集成更多监控和告警功能
- [ ] 支持插件扩展
- [ ] Web 版本发布
- [ ] 移动端支持

## 🤝 贡献指南

我们欢迎任何形式的贡献！请查看 [贡献指南](CONTRIBUTING.md) 了解详细信息。

### 如何贡献
1. Fork 本仓库
2. 创建功能分支 (`git checkout -b feature/AmazingFeature`)
3. 提交更改 (`git commit -m 'Add some AmazingFeature'`)
4. 推送到分支 (`git push origin feature/AmazingFeature`)
5. 创建 Pull Request

## 📞 支持与反馈

- **问题报告**: [GitHub Issues](../../issues)
- **功能请求**: [GitHub Discussions](../../discussions)
- **文档**: [Wiki](../../wiki)

## 📄 许可证

本项目基于 MIT 许可证开源 - 查看 [LICENSE.txt](LICENSE.txt) 文件了解详细信息。

## 🙏 致谢

感谢以下开源项目的支持：
- [Avalonia UI](https://avaloniaui.net/) - 跨平台 .NET UI 框架
- [Kubernetes Client](https://github.com/kubernetes-client/csharp) - .NET Kubernetes 客户端
- [Semi Design](https://semi.design/) - 现代化设计系统

---

<div align="center">

注意现在的版本是未完成版！

**⭐ 如果这个项目对你有帮助，请给我们一个 Star！**

Made with ❤️ by KubeSpeed Team

</div>
