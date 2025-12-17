# Vercel CLI Link 指南

## Link to Existing Project 时输入什么？

### 项目名称规则

当 Vercel CLI 要求输入项目名称时，应该输入：

1. **Vercel Dashboard 中的项目名称**（不是 GitHub 仓库名）
   - 登录 https://vercel.com
   - 查看你的项目列表
   - 使用项目卡片上显示的名称

2. **如果项目名和仓库名相同**，可以直接使用 GitHub 仓库名

### 你的情况

- GitHub 仓库名：`CodeAlchemist`
- 本地项目名：`ai-recruitment-app`

### 操作步骤

#### 方法一：查看 Vercel Dashboard（推荐）

1. 登录 https://vercel.com
2. 查看项目列表
3. 找到对应的项目，查看项目名称
4. 在 CLI 中输入该名称

#### 方法二：让 CLI 列出所有项目

运行 `vercel link` 时：
- 选择 "Link to existing project"
- CLI 会列出你账号下的所有项目
- 使用方向键选择，不需要手动输入名称

#### 方法三：直接输入（如果确定名称）

```bash
vercel link
# 选择: Link to existing project
# 输入: CodeAlchemist (或你在 Dashboard 中看到的项目名)
```

### 如果项目不存在

如果输入名称后提示找不到项目：

1. **检查是否在正确的 Vercel 账号/团队下**
   ```bash
   vercel whoami  # 查看当前登录的账号
   ```

2. **在 Dashboard 中创建新项目**
   - 访问 https://vercel.com/new
   - 导入 GitHub 仓库 `CodeAlchemist`
   - 项目会自动创建，名称通常是仓库名

3. **或者选择 "Set up a new project"**
   ```bash
   vercel link
   # 选择: Set up a new project
   # 输入项目名: ai-recruitment-app (或你想要的名称)
   ```

### 完整流程示例

```bash
# 1. 登录（如果还没登录）
vercel login

# 2. 链接项目
vercel link

# 3. 选择选项
# ? Set up and deploy "~/proj/ai-recruitment-app"? [Y/n] y
# ? Which scope do you want to deploy to? [选择你的账号/团队]
# ? Link to existing project? [y/N] y
# ? What's the name of your existing project? [输入项目名或从列表选择]

# 4. 部署
vercel --prod
```

### 查看已链接的项目

```bash
cat .vercel/project.json
```

这会显示当前链接的 Vercel 项目信息。




