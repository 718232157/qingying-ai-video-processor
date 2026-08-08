# 清影 Qingying

> **中文长视频目标词处理桌面软件**
> 本地完成语音识别、目标词定位、处理结果校验与视频导出。

<p align="center">
  <img src="assets/qingying-workflow-demo.jpg" alt="清影长视频目标词处理工作台" width="100%" />
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Desktop-Electron-47848F?style=flat-square&logo=electron" alt="Electron" />
  <img src="https://img.shields.io/badge/Frontend-React%20%2B%20TypeScript-61DAFB?style=flat-square&logo=react&logoColor=111" alt="React and TypeScript" />
  <img src="https://img.shields.io/badge/AI-PyTorch%20%2B%20FunASR-EE4C2C?style=flat-square&logo=pytorch" alt="PyTorch and FunASR" />
  <img src="https://img.shields.io/badge/Media-FFmpeg-007808?style=flat-square&logo=ffmpeg" alt="FFmpeg" />
</p>

## 项目概述

清影是一款面向中文长视频场景的本地 AI 工具。用户导入视频并输入目标词后，系统将语音识别结果、命中位置、时间轴与视频预览汇集到统一工作台，协助完成处理范围确认，并导出处理后的视频。

## 我解决的问题

- **长视频难检索**：将非结构化语音转为可定位的文本与时间信息，降低人工逐段试听成本。
- **处理结果难确认**：通过命中高亮、时间轴和视频预览，让用户能在导出前核验处理位置。
- **桌面端 AI 工程化**：将 Python 推理与媒体处理能力封装为桌面应用可调用的本地服务，提供任务进度、缓存管理和安装包交付能力。

## 核心技术

| 方向 | 技术与实践 |
| --- | --- |
| 桌面应用 | **Electron + React 19 + TypeScript**；使用 IPC 协调界面、本地服务与文件系统能力 |
| AI 语音处理 | **Python 3.11、PyTorch、TorchAudio、FunASR、ModelScope、pypinyin**；完成中文语音转写、时间对齐与目标词候选定位 |
| 音视频工程 | **FFmpeg** 进行媒体预处理、音频处理与视频导出；导出时保留原视频流并替换音频轨 |
| 本地服务 | Python HTTP 服务与 **SQLite**，承载本地任务、授权与数据管理能力 |
| 工程化交付 | Vite / electron-vite、Electron Builder、NSIS；构建 Windows x64 安装包并支持版本更新配置 |

## 端到端处理流程

```mermaid
flowchart LR
    A["导入长视频 / 输入目标词"] --> B["音视频预处理"]
    B --> C["中文语音识别与时间对齐"]
    C --> D["目标词候选定位"]
    D --> E["转写文本、时间轴、视频预览校验"]
    E --> F["音频处理与正常内容复核"]
    F --> G["FFmpeg 导出处理后视频"]
```

## 产品能力

- 中文目标词检索与批量处理
- 长视频转写、命中高亮、时间轴定位与预览
- 处理进度反馈、导出与缓存清理
- 本地授权、公告与客户端更新能力

## 个人职责

- 负责 Electron 桌面端、React 交互界面与 Python AI 处理链路的端到端开发。
- 完成语音识别、时间定位、候选复核与 FFmpeg 导出的集成，重点关注目标词命中与正常音频保护。
- 完成 Windows 安装包、运行时依赖、版本更新与本地授权相关工程化建设。

---

> 本仓库为个人项目案例展示，包含产品说明、技术方案与界面演示。
> 出于商业与数据安全考虑，核心算法实现、模型运行时、授权服务及业务素材不对外公开。
