# Acraw

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
git clone https://github.com/0u2y/Acraw.git
cd media-crawler-gui

# 2. 安装依赖
uv pip install jieba wordcloud matplotlib pillow curl-cffi

# 3. 复制配置模板
cp config.example.json config.json
# （Windows: copy config.example.json config.json)
```
---

**❓ 常见问题**

**Q1：双击 exe 黑窗一闪而过**

**排查：**

```bash
path.exe
```
或查看 install.log / crash.log。

**Q2：B站抓取报 code=-352 风控**
原因：IP 被 B站风控。

**解决：**

点「测试 SESSDATA」确认 SESSDATA 有效

1.加代理

2.或换 aicu.cc 数据源

3.或等 10-30 分钟

**Q3：切换语言后输入框清空**

**解决：**

更新到最新版，已保存 9 项 UI 状态。

**Q4：安装依赖失败**

```bash
uv pip install -i https://pypi.tuna.tsinghua.edu.cn/simple jieba wordcloud matplotlib pillow
```

**Q5：抖音抓取超时**

**解决：**

1.加代理

2.加大延迟

3.确认已扫码登录

**Q6：词云中文显示方框**

**解决：**

1.Windows：安装微软雅黑

2.Linux：sudo apt install fonts-wqy-microhei

3.macOS：系统自带 PingFang

---

**🔐 安全说明**
**措施**	                            **说明**

Token 混淆	  SESSDATA / bili_jct / Apify Token 以 XOR + Base64 存储

路径脱敏	      日志中路径显示为 .../最后两级/

Cookie 脱敏	  日志中 SESSDATA=***

代理 URL 校验	只允许 http/https/socks5/socks5h

响应大小限制	  32 MB 上限

配置文件原子写	临时文件 + os.replace

文件权限	0o600（Linux/macOS）

⚠️ XOR 混淆不是强加密，只防肉眼直读。如需强安全，请使用系统 keyring。

---

## 📄 License

本项目采用 [MIT License](LICENSE) 开源协议。
