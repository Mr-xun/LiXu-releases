# 理序 LiXu

**看懂文件，处理有序。**

理序 LiXu 是一款本地优先的桌面文件工作台，用来整理混乱文件、核对材料、加工 PDF 和图片，并把结果保存成可继续使用或交付的副本。

[![最新稳定版](https://img.shields.io/github/v/release/Mr-xun/LiXu-releases?label=latest%20stable)](https://github.com/Mr-xun/LiXu-releases/releases/latest)
[![下载安装包](https://img.shields.io/badge/download-GitHub%20Releases-24292f)](https://github.com/Mr-xun/LiXu-releases/releases)

应用源码保存在独立私有仓库。这个公开仓库只用于发布安装包、版本说明和收集问题反馈，不提供源码或开放环境安装入口。

- [产品官网与界面预览](https://mr-xun.github.io/LiXu-releases/)
- [下载安装包](https://github.com/Mr-xun/LiXu-releases/releases)
- [问题反馈与建议](https://github.com/Mr-xun/LiXu-releases/issues)

## 主要功能

### 文件工作台

- 预览图片、PDF、Office 文档和文本
- 多选文件、搜索、目录浏览和快捷操作
- macOS Finder「快速操作」与 Windows「发送到」入口
- 任务、执行记录和来源核对

### AI 文件整理

- 读取正文和视觉预览，生成建议名称与目标目录
- 支持行内修改、待确认筛选、单条重解析和批量处理
- 识别并发支持 `1–32` 档调节，并对 `429` 限流自动退避
- 默认生成整理副本，保留原件；原位改名或移动需要明确确认

### 材料准备与交付

- 从通知或要求中提取格式、尺寸、体积等条件
- 核对材料缺项和匹配关系
- 生成统一副本或带来源清单的 ZIP 交付包

### PDF 与图片加工

- PDF 合并、页码提取、拆分、排序和旋转
- 图片转 PDF、JPG / PNG / WebP 转换、缩放和压缩
- 输出前检查页数、大小、来源和文件冲突

### 模型连接

- 支持 OpenAI Chat Completions / Responses 与 Anthropic Messages
- 按任务绑定模型和视觉能力
- API Key 保存在当前设备的系统加密凭据存储中

## 功能截图

![文件工作台](screenshots/workbench-light.png)

*文件工作台：选择文件、预览内容并进入整理流程。*

![AI 文件整理](screenshots/archive-live-light.png)

*AI 文件整理：查看建议目录和文件名，逐项确认后生成副本。*

![材料准备结果](screenshots/materials-result-light.png)

*材料准备：核对材料状态并生成可追溯的交付结果。*

截图来自 `v0.1.0`，使用合成示例数据，不包含真实文件、账号或 API Key。

## 下载与安装

当前仅通过 [GitHub Releases](https://github.com/Mr-xun/LiXu-releases/releases) 提供桌面安装包：

| 平台 | 适用设备 | 文件格式 |
| --- | --- | --- |
| macOS Apple Silicon | M1 / M2 / M3 / M4 | `LiXu-<版本号>-mac-arm64.dmg` 或 `.zip` |
| macOS Intel | Intel 处理器 Mac | `LiXu-<版本号>-mac-x64.dmg` 或 `.zip` |
| Windows 64 位 | Windows 10 / 11 x64 | `LiXu-<版本号>-win-x64.exe` |

### 版本通道

- **稳定版**：没有 `Pre-release` 标记，适合日常使用；当前稳定版为 `v0.1.0`。
- **预览版**：版本号带有 `alpha`、`beta` 或 `rc`，GitHub 会标记为 `Pre-release`，用于提前体验和反馈。

### 首次打开

当前安装包尚未接入商业签名与公证：

- **macOS**：如提示无法验证开发者或应用已损坏，请右键点击应用选择「打开」，或在「系统设置 → 隐私与安全性」中允许打开。
- **Windows**：如出现 SmartScreen 提示，请先核对 SHA-256，再点击「更多信息 → 仍要运行」。

安装或更新前，请先等待应用内正在运行的文件任务完成。

### 校验安装包

每个 Release 均附带 `SHA256SUMS.txt`：

```bash
shasum -a 256 -c SHA256SUMS.txt --ignore-missing
```

Windows PowerShell：

```powershell
Get-FileHash .\LiXu-<版本号>-win-x64.exe -Algorithm SHA256
```

## 隐私与安全边界

- 文件浏览、PDF / 图片加工和执行记录默认在本地完成。
- 只有在你明确启动 AI 整理或材料核对后，必要的文字或低尺寸图片预览才会发送到你选择的模型服务。
- 文件夹「仅保留结构」时，不会向模型发送文件内容。
- 整理和加工默认生成副本，原件保持不变。
- API Key 不写入导出清单、源码或错误日志。

## 问题反馈

请通过 [GitHub Issues](https://github.com/Mr-xun/LiXu-releases/issues) 反馈问题，并附上：

1. 操作系统及架构，例如 macOS 15 arm64 或 Windows 11 x64
2. 应用版本号，例如 `v0.1.0`
3. 可复现的操作步骤和实际结果
4. 经过脱敏的错误提示

请不要上传 API Key、Authorization 头、私人证件或敏感原文件。

## 许可与第三方组件

理序 LiXu 以专有软件形式分发。公开安装包和发布说明不表示公开应用源码或授予开源许可。安装包中的第三方组件仍按各自许可证提供，相关声明随安装包分发。
