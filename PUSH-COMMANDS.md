# 推送到 GitHub 的命令

## 步骤 1：在 GitHub 创建仓库

访问：https://github.com/new

- Repository name: `ip-discovery`
- Description: `个人IP定位发现助手 - WorkBuddy Plugin`
- 选择 **Public**（公开仓库）
- 不要勾选 "Add a README file"（我们已经有了）
- 点击 **Create repository**

## 步骤 2：推送代码

在 PowerShell 中执行以下命令：

```powershell
cd "D:\AICode\SKXCopy\ip-discovery"
git push -u origin main
```

如果提示输入用户名和密码：
- 用户名：`Davidxiong513`
- 密码：使用 GitHub Personal Access Token（不是登录密码）

### 如何创建 GitHub Token

1. 访问：https://github.com/settings/tokens
2. 点击 **Generate new token (classic)**
3. 勾选 `repo` 权限
4. 生成后复制 token，作为密码使用

## 步骤 3：验证

推送成功后，访问：
https://github.com/Davidxiong513/ip-discovery

确认文件都已上传。

## 步骤 4：用户安装命令

告诉用户用这个命令安装你的插件：

```bash
/plugin marketplace add Davidxiong513/ip-discovery
```

或者：

```bash
/plugin marketplace add https://github.com/Davidxiong513/ip-discovery.git
```

---

✅ 完成！你的插件就会出现在 WorkBuddy 的 SkillHub 市场里了。
