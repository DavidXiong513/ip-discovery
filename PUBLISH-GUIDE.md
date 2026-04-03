# IP Discovery 插件 — GitHub市场发布方案

> 创建日期：2026-04-03
> 作者：思考熊（借假修真）

---

## 一、发布前检查清单

### 1.1 仓库结构确认
```
ip-discovery/
├── marketplace.json              ✅ 已完成
├── README.md                     ✅ 已完成
├── LICENSE                       ✅ 已完成（MIT）
├── commands/
│   └── ip-discovery.md           ✅ 已完成
└── skills/
    ├── ip-discovery/
    │   ├── SKILL.md              ✅ 已完成
    │   ├── references/
    │   │   ├── ip-dimensions.md  ✅ 已完成
    │   │   └── question-bank.md  ✅ 已完成
    │   └── assets/
    │       └── ip-profile-template.md  ✅ 已完成
    ├── content-strategy/
    │   └── SKILL.md              ✅ 已完成
    └── audience-analysis/
        └── SKILL.md              ✅ 已完成
```

### 1.2 marketplace.json 检查
- [ ] `name`、`description`、`version` 字段已填写
- [ ] 所有 skills 的 `path` 与实际目录结构一致
- [ ] `repository` URL 已更新为实际的GitHub仓库地址
- [ ] `tags` 包含有助于搜索的关键词

### 1.3 SKILL.md 检查
- [ ] YAML frontmatter 包含 `name`、`description`（必需字段）
- [ ] `name` 使用 kebab-case 格式
- [ ] `description` 控制在160字符以内
- [ ] 核心指令清晰、可执行
- [ ] 交互原则和边界条件已定义

### 1.4 README.md 检查
- [ ] 包含项目名称、简介、核心功能
- [ ] 安装说明清晰（至少2种安装方式）
- [ ] 使用方法有具体示例
- [ ] 包含常见问题（FAQ）
- [ ] 包含作者信息和许可证链接

---

## 二、发布步骤

### 2.1 创建GitHub仓库

1. 登录 GitHub，点击 "New Repository"
2. 仓库名称：`ip-discovery`（或自定义）
3. 描述：`通过六维度结构化访谈帮用户发现个人IP定位 - CodeBuddy/WorkBuddy Skill插件`
4. 选择 **Public**（公开仓库，才能通过市场分发）
5. 勾选 **Add a README file**（如果本地已有则不需要）
6. 点击 **Create repository**

### 2.2 推送代码

```bash
# 进入插件目录
cd D:\AICode\SKXCopy\ip-discovery

# 初始化（如果还没有.git）
git init

# 添加远程仓库（替换为你的实际仓库地址）
git remote add origin https://github.com/your-username/ip-discovery.git

# 添加所有文件
git add .

# 首次提交
git commit -m "feat: IP Discovery v1.0.0 - 六维度个人IP定位助手"

# 推送到主分支
git push -u origin main
```

### 2.3 配置仓库（增强展示效果）

#### 添加 Topics（标签）
在仓库页面点击 "About" 旁边的齿轮图标，添加以下 topics：
```
codebuddy, workbuddy, skill, plugin, ip-positioning, personal-brand,
个人IP, 个人品牌, 自媒体, ip定位, content-strategy
```

#### 添加 Social Preview
- 在仓库根目录创建 `.github/social-preview.png`（1200x630px）
- 展示插件的核心功能和六维度模型的可视化

#### 添加 GitHub Actions（可选）
自动检查 SKILL.md 格式的有效性：
```yaml
# .github/workflows/validate.yml
name: Validate Skills
on: [push, pull_request]
jobs:
  validate:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Check SKILL.md files
        run: |
          find skills -name "SKILL.md" | while read f; do
            echo "Validating $f..."
            # 检查YAML frontmatter
            head -1 "$f" | grep -q "^---" || { echo "Missing frontmatter in $f"; exit 1; }
            echo "$f OK"
          done
```

---

## 三、市场注册与分发

### 3.1 用户安装方式

#### 方式A：通过命令添加市场
```bash
# 在 CodeBuddy/WorkBuddy 中执行
/plugin marketplace add your-username/ip-discovery
```

#### 方式B：通过 settings.json 配置（团队场景）
```json
{
  "extraKnownMarketplaces": {
    "ip-discovery-market": {
      "source": {
        "source": "github",
        "repo": "your-username/ip-discovery"
      }
    }
  },
  "enabledPlugins": {
    "ip-discovery@ip-discovery-market": true
  }
}
```

### 3.2 提交到官方市场（进阶）

如果想要被更多人发现，可以尝试提交到 CodeBuddy 官方市场：

1. 准备一份简短的插件介绍（中英文）
2. 在 [CodeBuddy 官方社区](https://github.com/TencentCloud) 发起 Issue 或 PR
3. 附上完整的功能说明和使用示例

---

## 四、推广策略

### 4.1 短期推广（发布后1-2周）

| 渠道 | 行动 | 目标 |
|------|------|------|
| **微信公众号** | 写一篇"我用AI做了个IP定位插件"的推文 | 粉丝+读者了解 |
| **即刻/X** | 发布简短介绍 + 使用截图 | 技术圈传播 |
| **V2EX** | 分享到"程序员"版块 | 开发者反馈 |
| **CSDN/知乎** | 写一篇"CodeBuddy Skill开发实战"教程 | 搜索流量 |
| **GitHub** | 给README加star，提交到awesome列表 | 开源社区曝光 |

### 4.2 中期优化（发布后1-3个月）

- 收集用户反馈，迭代SKILL.md的问题库
- 补充更多IP定位案例（可以作为 references/ 目录下的案例库）
- 根据使用数据优化访谈流程的节奏
- 添加更多语言支持（英文版SKILL.md）

### 4.3 长期规划（3个月+）

- **增强版**：集成MCP Server（小红书/公众号数据分析）
- **案例库**：收集并展示真实的IP定位成功案例
- **协作版**：支持团队IP定位（适用于MCN/创业团队）
- **商业化**：免费基础版 + 付费深度版

---

## 五、商业化潜力分析

### 5.1 免费版（当前）
- 基础的IP定位访谈流程
- 标准IP画像报告输出
- 3个Skill全部开放

### 5.2 付费增强版（未来）
| 功能 | 免费版 | 付费版 |
|------|--------|--------|
| IP定位访谈 | ✅ | ✅ |
| IP画像报告 | ✅ | ✅ |
| 内容策略 | ✅ | ✅ |
| 受众分析 | ✅ | ✅ |
| 竞品IP拆解 | ❌ | ✅ |
| 平台数据抓取 | ❌ | ✅ |
| 1对1咨询对接 | ❌ | ✅ |
| 定制化模板 | ❌ | ✅ |
| 持续迭代指导 | ❌ | ✅ |

### 5.3 品牌价值

- 作为"思考熊"IP的技术产品输出，增强IP的专业性和影响力
- 建立开发者社区中的个人品牌
- 为未来的知识付费产品（IP定位课程/咨询）积累素材和口碑

---

## 六、风险与注意事项

1. **GitHub仓库必须公开**，私有仓库无法通过市场分发
2. **marketplace.json 格式要严格正确**，否则安装会失败
3. **SKILL.md 的 name 必须全局唯一**，避免与其他插件冲突
4. **注意隐私**，访谈过程中不要收集或存储用户的敏感信息
5. **版本管理**，后续更新要遵循语义化版本规范

---

*本方案为参考指南，实际发布时请根据GitHub和CodeBuddy的最新规范进行调整。*
