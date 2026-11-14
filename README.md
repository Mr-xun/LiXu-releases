# 理序 LiXu

**看懂文件，处理有序。** 本地优先的 AI 文件整理、材料核对与 PDF / 图片加工工作台。

这里用于发布 **理序 LiXu** 桌面安装包、版本更新说明与收集问题反馈。应用源码保存在独立私有仓库，不在此公开仓库开放。

- **产品官网与界面预览**：[mr-xun.github.io/LiXu-releases](https://mr-xun.github.io/LiXu-releases/)
- **下载安装包（Releases）**：[github.com/Mr-xun/LiXu-releases/releases](https://github.com/Mr-xun/LiXu-releases/releases)
- **问题反馈与建议（Issues）**：[github.com/Mr-xun/LiXu-releases/issues](https://github.com/Mr-xun/LiXu-releases/issues)

---

## 核心能力

| 模块 | 主要功能 |
| --- | --- |
| **文件工作台** | 只读预览图片、PDF 与文本，支持多选、悬浮快捷圆环及系统右键快捷入口（macOS「快速操作」/ Windows「发送到」） |
| **AI 文件整理** | 读取文档正文与视觉预览并流式生成新名称与目标目录；支持行内直接改名、待确认核对、单条重解析、1–32 可调识别并发与自动限流退避 |
| **材料准备与交付** | 解析提交通知并逐项核对格式、尺寸与体积，输出统一副本或带来源清单的 ZIP 交付包 |
| **PDF 与图片加工** | 本地 PDF 页序重排、旋转、删除与合并、图片转 PDF；图片批量转 JPG / PNG / WebP 与压缩缩放 |
| **多模型连接中心** | 支持 OpenAI Chat Completions / Responses 与 Anthropic Messages 接口，按任务分别绑定模型，密钥加密保存在本机系统钥匙串 |

---

## 下载与安装

前往 [Releases 页面](https://github.com/Mr-xun/LiXu-releases/releases) 下载对应系统与架构的安装包：

| 平台 | 适用设备 | 安装包文件名格式 |
| --- | --- | --- |
| **macOS（Apple Silicon）** | M1 / M2 / M3 / M4 系列芯片 | `LiXu-<版本号>-mac-arm64.dmg` 或 `.zip` |
| **macOS（Intel）** | Intel 处理器 Mac | `LiXu-<版本号>-mac-x64.dmg` 或 `.zip` |
| **Windows（64 位）** | Windows 10 / 11 x64 | `LiXu-<版本号>-win-x64.exe` |

### 预览版与首次打开说明

- 标有 **`Pre-release`** 的版本为公开预览版；当前以 macOS Apple Silicon 实机验证为主，Windows x64 与 Intel Mac 安装包由自动构建生成并持续完善实机验收。
- **尚未接入商业签名与公证**：
  - **macOS**：首次打开如提示“无法验证开发者”或“已损坏”，请右键点击 `理序 LiXu.app` 选择「打开」，或在「系统设置 → 隐私与安全性」中点击「仍要打开」。
  - **Windows**：如弹出 Microsoft Defender SmartScreen 提示，可先核对下方 SHA-256 校验值后点击「更多信息 → 仍要运行」。
- 安装或更新前，请先等待应用内正在运行的文件任务完成。

### 完整性校验（SHA-256）

每个 Release 均附带 `SHA256SUMS.txt`，可在下载后核对文件指纹：

- **macOS（终端）**：
  ```bash
  shasum -a 256 -c SHA256SUMS.txt --ignore-missing
  ```
- **Windows（PowerShell）**：
  ```powershell
  Get-FileHash .\LiXu-<版本号>-win-x64.exe -Algorithm SHA256
  ```

---

## 隐私与安全边界

- **本地优先**：文件浏览、PDF/图片加工与执行日志默认在本地完成，不强制上传云端存储或绑定账号。
- **可控发送范围**：仅在你明确启动 AI 整理或材料核对并选择模型后，提取必要的文字或低尺寸图片预览发送给所选模型接口；「仅保留结构」整组文件夹不向模型发送文件内容。
- **默认输出副本**：整理与加工默认在单独输出目录（默认 `文稿/LiXu/整理结果`）生成副本并保留原件；同卷原位整理与条件撤销需显式开启并核对范围。
- **本机隔离密钥**：模型 API Key 仅保存于当前设备的系统加密凭据存储，不写入共享配置、导出清单或错误日志。

---

## 问题反馈

遇到问题或有功能建议，欢迎提交 [GitHub Issue](https://github.com/Mr-xun/LiXu-releases/issues)。提交时请尽量附带：

1. 操作系统及架构（例如 macOS 15 arm64 / Windows 11 x64）
2. 应用版本号（显示在软件左下角，如 `v0.1.0-alpha.26`）
3. 清晰的重现步骤与实际/预期结果
4. 经过脱敏的错误提示或日志（**切勿附带 API Key、Authorization 头、私人证件或敏感原文件**）

---

## 许可与第三方组件声明

**理序 LiXu** 当前以专有软件形式分发，公开安装包及发布说明不表示公开应用源码或授予开源许可。安装包内包含的开源第三方组件（如 FFmpeg 媒体组件等）仍按各自许可证提供，相关许可证、构建信息及对应源码说明随安装包一同分发。
