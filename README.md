# 🧭 IP Discovery — 个人IP定位发现助手

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

> 通过六维度结构化访谈，系统化地帮你发现并定义个人IP定位。

## ✨ 功能特点

- **六维度IP定位模型**：专业基因 → 价值主张 → 独特视角 → 目标受众 → 表达风格 → 长期愿景
- **阶段性交付机制**：每轮对话都有小结卡片，让用户感受到积累
- **3个斜杠命令**：快速评估、完整发现、内容策略规划
- **3个配套Skill**：IP发现、内容策略、受众分析

## 🚀 快速开始

### 安装

在 WorkBuddy中的技能市场中搜索“Ip-Discovery”，点击安装即可~

### 使用

| 命令 | 用途 | 耗时 |
|------|------|------|
| `/ip-quick [自我介绍]` | 快速IP定位评估 | 2分钟 |
| `/ip-discovery` | 完整IP发现流程 | 15-20分钟 |
| `/content-plan` | 基于IP定位生成内容策略 | 5分钟 |

## 📁 目录结构

```
ip-discovery/
├── .codebuddy-plugin/
│   └── marketplace.json          # 市场清单（CodeBuddy官方标准）
├── ip-discovery/                 # 插件目录
│   ├── plugin.json               # 插件清单
│   └── .codebuddy/
│       ├── commands/             # 斜杠命令
│       │   ├── ip-discovery.md
│       │   ├── ip-quick.md
│       │   └── content-plan.md
│       └── skills/               # 技能定义
│           ├── ip-discovery/
│           │   ├── SKILL.md
│           │   ├── references/
│           │   │   ├── ip-dimensions.md
│           │   │   └── question-bank.md
│           │   └── assets/
│           │       └── ip-profile-template.md
│           ├── content-strategy/
│           │   └── SKILL.md
│           └── audience-analysis/
│               └── SKILL.md
├── README.md
├── LICENSE
└── PUBLISH-GUIDE.md
```

## 🎯 适用人群

- 想做自媒体但不知道发什么内容的人
- 想打造个人品牌但定位模糊的人
- 职业转型期需要重新梳理价值的人
- 已经有IP但想系统优化定位的人

## 📄 许可证

MIT License

## 🤝 贡献

欢迎提交 Issue 和 PR！
