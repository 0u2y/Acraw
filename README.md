# MediaCrawler GUI

> 基于 Tkinter 的图形化爬虫控制台，支持 **B站 / 抖音 / 贴吧 / Reddit** 四平台的数据采集、查看、导出与词云生成。

**注意！该程序完全由DEEPSEEK生成,若有安全性问题,本人概不负责**

![Python](https://img.shields.io/badge/Python-3.11+-blue.svg)
![License](https://img.shields.io/badge/License-MIT-green.svg)
![Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20macOS%20%7C%20Linux-lightgrey.svg)

---

#✨ 功能特性

| 平台 | 采集类型 | 登录态 | 代理 | 词云 |
|---|---|---|---|---|
| **B站** | 用户信息 / 用户评论 | SESSDATA | ✅ | ✅ |
| **抖音** | 指定视频 / 创作者主页 | 扫码 | ✅ | ✅ |
| **贴吧** | 关键词搜索 / 帖子 / 用户 | 扫码 | ✅ | ✅ |
| **Reddit** | 按用户名 | Apify Token | — | ✅ |

**其他特性**：

- 🗂️ JSONL数据管理（加载/删除/导出CSV/SHA256校验）
- 🔍 关键字过滤、按帖子分组
- 🌏 中英文双语切换
- 🌥️ 一键生成中文词云
- 🔐 Token混淆存储、路径脱敏、审计日志
- 📦 一键安装依赖向导

---

## 🚀快速开始

### 环境要求

- **Python 3.11+**：[下载](https://www.python.org/downloads/)
- **uv**（可选但推荐）：[下载](https://docs.astral.sh/uv/)
- **MediaCrawler 项目**：[GitHub](https://github.com/NanmiCoder/MediaCrawler)
- **Chrome / Chromium**（抖音、贴吧需要）

### 安装

```bash
# 1. 克隆本仓库
git clone https://github.com/你的用户名/media-crawler-gui.git
cd media-crawler-gui

# 2. 安装依赖
uv pip install jieba wordcloud matplotlib pillow curl-cffi

# 3. 复制配置模板
cp config.example.json config.json
# （Windows: copy config.example.json config.json)
```
## 📄 License

本项目采用 [MIT License](LICENSE) 开源协议。
