# 课后测答题程序

一个纯静态的英语单词课后测答题网页，题目严格来自《课后测1/2/3补测》表格（每套 50 词）。

- 无需服务器、无需数据库，单文件 `index.html`
- 手机/电脑浏览器均可使用（针对安卓手机浏览器优化）
- 两种模式：看英文选中文、看中文选英文
- 每题 4 选 1，即时判分，结束后有得分、错题回顾、错题重练

## 在线使用（GitHub Pages 部署）

### 方式一：网页上传（最简单）

1. 登录 GitHub，右上角 **+** → **New repository**，新建仓库（如 `quiz`），选 Public。
2. 仓库页点 **Add file → Upload files**，把本目录的 `index.html` 拖进去，点 **Commit changes**。
3. 进入 **Settings → Pages**，在 **Build and deployment** 下把 Source 设为
   **Deploy from a branch**，Branch 选 **main** / **/(root)**，点 Save。
4. 等 1~2 分钟，访问 `https://<你的用户名>.github.io/quiz/` 即可答题。
   （手机浏览器直接打开这个网址就行，建议发送到桌面当 App 用。）

### 方式二：Git 命令行

```bash
git init
git add index.html
git commit -m "feat: 课后测答题程序"
git branch -M main
git remote add origin https://github.com/<你的用户名>/quiz.git
git push -u origin main
# 然后同方式一第 3 步开启 Pages
```

## 修改题目

题目数据嵌在 `index.html` 里 `const DATA = {...}` 一行中，格式：

```json
{ "t1": { "title": "课后测试1补测", "items": [ { "en": "fashion", "zh": "v.制定 n. 时尚" }, ... ] }, ... }
```

按同样格式增删改词条后重新上传即可。
