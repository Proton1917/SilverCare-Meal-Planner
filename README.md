# 银龄膳养助手（SilverCare Meal Planner）

一款面向老年人的单页食谱规划工具，集 BMI 评估、慢病适配、菜谱打分、茶饮与水果推荐于一体。网页内置居民/食堂/配送三端原型，可直接部署在 GitHub Pages，实现零后端的健康膳食参考服务。

---

## 功能概览
- **多端入口**：居民端记录档案并生成个性化菜谱，食堂/配送端支持配餐与营养换算提醒。
- **数据驱动**：扩展菜库、茶饮/水果建议、慢病参数化打分全部写入 `index.html`，可随时编辑。
- **轻量部署**：纯静态 HTML，无依赖库，拖到任何支持静态文件的托管平台即可运行。

---

## 目录结构

```
app测试/
├── index.html          # 主站点（单文件页面，含样式与脚本）
└── README.md           # 当前说明文档
```

---

## 本地预览
1. 双击 `index.html` 用浏览器打开即可。
2. 建议使用 Chrome/Edge 最新版本以获得更完整的本地存储体验。

---

## GitHub Pages 部署方案

### 1. 准备工作
1. 注册/登录 GitHub：https://github.com
2. 安装 Git  
   ```bash
   # macOS (Homebrew)
   brew install git
   # 其他平台可从 https://git-scm.com/downloads 下载
   ```

### 2. 初始化仓库并推送

```bash
cd /Users/gordongauerk/Desktop/计算机软件开发/app测试
git init

git add index.html README.md
git commit -m "初始提交：银龄膳养助手"

git remote add origin https://github.com/你的用户名/silvercare-meal-planner.git
git branch -M main
git push -u origin main
```

### 3. 启用 GitHub Pages
1. 打开仓库 Settings → Pages
2. Source 选择 `main` 分支
3. Folder 选择 `/ (root)`
4. 保存后等待约 1 分钟，访问 `https://你的用户名.github.io/silvercare-meal-planner/`

### 4. 自定义域名（可选）
```bash
echo "www.example.com" > CNAME
git add CNAME
git commit -m "Add custom domain"
git push
```
随后在域名服务商添加 `CNAME` 记录指向 `你的用户名.github.io`，等待 DNS 生效。

### 5. 更新网页
```bash
# 修改 index.html 后
git add index.html
git commit -m "更新内容"
git push
```
GitHub Pages 会自动重新部署，通常 1 分钟内生效。

---

## 成本与时间

| 项目          | GitHub Pages |
|---------------|--------------|
| 注册 / 托管   | 免费         |
| 自定义域名    | 约 ¥50/年（可选） |
| 开发难度      | 极低（直接上传 HTML） |
| 首次上线时间  | 约 10 分钟 |

---

## 快速场景
- 向导师/客户演示老年健康食谱原型
- 为社区/养老院提供在线膳食示例
- 作为前端 Demo，用于展示数据驱动的表单与本地存储交互

---

## 常见问题

**Q: GitHub Pages 加载慢怎么办？**  
可在 Gitee Pages 复刻同一仓库，流程类似且访问速度更友好。

**Q: 如何添加更多菜谱或规则？**  
直接在 `index.html` 中修改 `DEFAULT_DISHES`、`DEFAULT_RULES` 等对象即可，保存后重新部署。

**Q: 可以绑定自定义域名吗？**  
可以，照前文步骤创建 `CNAME` 并配置 DNS。

**Q: 能否接入后端或数据库？**  
可以在页面中通过 `fetch` 调用云函数、Serverless 或自建 API；GitHub Pages 对外部请求无特殊限制。

---

## 总结
- **银龄膳养助手** 提供一站式的老年饮食建议，涵盖 BMI、慢病、茶饮/水果等多维度内容。
- 单文件架构让部署与维护极其简单，适合个人/团队快速演示或投产。
- 后续如需动态能力，可在保持静态站点的基础上接入独立 API。

---

**版本**: v1.0  
**最后更新**: 2025-01  
**推荐部署耗时**: GitHub Pages ≈ 10 分钟
