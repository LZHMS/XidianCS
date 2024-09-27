---
comments: true
---
# 贡献指南

本学长组竭诚邀请各位计科学子为仓库建设共享自己的宝贵力量！只要你要意愿，我们都会非常欢迎，以下提供了基本的贡献指南。

## 本地构建
1. 克隆本项目 repo
    ```shell
    $ git clone https://github.com/LZHMS/XidianCS.git
    $ cd XidianCS
    ```
2. 激活 conda 虚拟环境
3. 安装 python 依赖（mkdocs 以及 material）
    ```shell
    $ pip install -r requirements.txt
    ```
4. 启动 mkdocs 本地服务
    ```shell
    $ mkdocs serve
    ```
    - 之后即可通过浏览器访问 localhost:8000 预览网站

## 贡献内容
### 网站结构
由于面向整个计算机科学与技术专业，本站内容根据计科大类基础以及计科小方向进行分组，然后在根据方向内所包含的课程单独分类，每个子类下包含有相应的课程，主要记录关于该课程的介绍、学习资料、学习建议等。

本站的核心语法仍然是 `markdown` 语言，每门课程都对应以课程英文简称/缩写命名，如果包含本地的图片资源，请在 `Images` 文件夹下创建相对于的目录结构，然后进行存放，其他资源同理。

站点的核心配置全部在`mkdocs.yml` 文件中定义，其中对应的文件目录结构需要在 `nav` 部分定义，尤其是新创建一个文件需要在其中添加对应的文件路径。

```text
.
├── docs
│   ├── BaoYan/               # 计科保研情况
│   ├── Configuration/        # 站点个性化配置
│   ├── CSBasic/              # 计科大类基础课
│   │   ├── General/            # 通识选修课
│   │   ├── Internation/        # 国际双创课
│   │   ├── Maths/              # 数理基础课
│   │   ├── Politics/           # 思政军体课
│   │   ├── ProfAny/            # 专业任选课
│   │   ├── ProfBase/           # 专业基础课
│   │   └── ProfCore/           # 专业核心课
│   ├── Home/                 # 主页文件夹
│   ├── Images/               # 图像资源
│   ├── Tables/               # 表格资源
│   ├── index.md              # 主页
│   ├── EmbeddedSystem/       # 计科嵌入式系统方向
│   ├── Intelligence/         # 计科大数据智能方向
│   ├── Network/              # 计科网络与信息安全方向
│   ├── SoftwareTheory/       # 计科软件与理论方向
│   └── Pilot/                # 计科试点班
├── mkdocs.yml          # mkdocs 站点设置
├── overrides/          # mkdocs-material 个性主题设置
├── README.md           # 站点、仓库介绍
└── requirements.txt    # 本站构建所需全部 python 依赖
```

### 贡献守则
我们非常欢迎你对本网站进行任何贡献，包括完善、更新页面内容，添加新页面，样式修改等等。但为了规范管理，也请遵循以下几条建议：

对于增添页面：

+ 如果你觉得该页面需要开启评论功能，请在页面顶部添加以下代码：
    ```markdown
    ---
    comments: true
    ---
    ```
    
+ 添加的新页面，一定记得将路径更新到 `mkdocs.yml` 文件中，否则无法访问；

对于页面内容：

+ 评价与建议：对于课程以及教师的评价，请尽量客观求是，避免主观色彩，也欢迎在课程页面下方评论；
+ 对于课程资源，请尽量插入链接，不要将资源内容直接写在页面中；如果有自己的网站，推荐放在自己的网站并在此插入链接
+ 尽量规范编写 `markdown`，注重页面的美观性，当然你尽管上传，我们发现后会及时进行修改；

### 贡献方式
#### Pull Request（推荐）
推荐通过 PR（即 Pull Request）的形式来进行贡献，具体流程：
##### 操作概述
- 在 GitHub 网页端点击右上角的 fork，将本仓库 fork 到自己的账号下，只克隆 `main` 分支就行；
- 在自己账号的对应仓库中进行修改；
- 修改完成后，点击 New pull request，提交一个 PR，注意选择 `master` 分支，其为选定的测试分支；
- 等待其他人审核、修改，然后合并到本 repo 中；

##### 详细步骤
1. 删除仓库原有 git 配置
    ```shell
    $ rm -rf .git
    ```
2. 初始化并配置自己的帐户和仓库
    ```shell
    $ git config user.name "Your Name"
    $ git config user.email "youremail@domain.com"
    $ git remote add origin https://github.com/YourName/YourRepo.git
    ```
3. 配置 Github Action 的工作流
    在 `.github/workflows/ci.yml` 文件中修改对应的 `user.name` 和 `user.email` 配置，内容如下：
    ```bash
    run: |
        git config user.name "Your Name"
        git config user.email "youremail@domain.com"
    ```
4. 初始化仓库并创建分支
    ```shell
    $ git init
    $ git branch -m main
    ```
    `.github/workflows/ci.yml` 文件中以下配置，表示 Github Action 在每次 push 到 `main` 分支时，自动构建并部署网站，因此在创建分支时，如果需要部署到自己仓库的 Page 页面则一定要选择 `main` 分支。
    ```bash
    on:
        push:
            branches: 
                - main
    ```
5. 修改并提交到仓库
    修改对应的内容完毕后，可以将其提交到自己的仓库中。
    ```shell
    $ git add .
    $ git commit -m "Your commit message"
    $ git push origin main
    ```
6. 在自己的仓库中开启 Github Pages
    如下图所示，对应 `Pages` 选项下，选择 `Deploy from a brach` 然后对应下方选择 `gh-pages` 分支，然后点击 `Save` 保存即可。这样等待部署完毕后，就可以在域名：`https://YourName.github.io/YourRepo` 中访问到本站了。
    <img src="https://lzhms.oss-cn-hangzhou.aliyuncs.com/images/docs/xdu/202409261133675.png" alt="Github Pages"/>
7. 提交 PR
    在自己的仓库中点击 `New pull request`，然后选择 `master` 分支，然后点击 `Create pull request`，等待审核即可。

#### 直接提交
对于在 Organization 中的同学，如果实在觉得 PR 过程有些复杂，也可以直接修改、提交到本仓库中（可以在线修改，也可以 clone 到本地修改然后 commit、push）。如果在提交中存在问题，我们后续会及时进行修改。（不过还是不推荐这种方式）

### 站点部署
本网站采用 Github Action 进行自动部署，所以如果你需要安装新的安装包，请将 `pip` 安装命令添加到对应的 `ci.yml` 文件中，并且修改对应的提交人信息包括 `user.name` 和 `user.email`。

选择部署到自己仓库，

+ 修改配置文件 `mkdocs.yml` 中的站点网址以及仓库名；
+ 修改 `ci.yml` 文件中的 `name` 和 `email`；
+ 提交到仓库，待自动部署完成后，开启 `page` 服务，选择 `gh-pages` 分支即可。

