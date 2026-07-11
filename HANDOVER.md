# 赛博浮生 · 项目交接文档

## 项目概况
- **项目名称**: 赛博浮生 (Cyber Fusheng)
- **类型**: 网页文字小游戏，灵感来自「北京浮生记」
- **技术栈**: 纯 HTML/CSS/JS 单文件，零外部依赖
- **部署目标**: GitHub Pages（静态站点，无需后端）

## 项目结构
```
cyber-fusheng-mvp/
├── index.html              # 游戏主文件（全部逻辑在此）
└── assets/
    ├── intro_bg.jpg        # 首页背景图
    ├── pixel_cover_v2.jpg  # 交易页面背景图
    └── sounds/
        └── M1.mp3          # 游戏背景音乐
```

## 当前已完成功能
- [x] 首页（带 Ken Burns 动效背景 + 扫描线 + 标题闪烁）
- [x] 交易主界面（左侧市场导航 + 中间报价 + 右侧仓库/场所）
- [x] 8 种商品，6 个市场，随机价格生成
- [x] 12 个商业事件 + 16 个人生事件（独立池，不重复触发）
- [x] 滚动新闻播报栏（10 条 2036 赛博风格新闻）
- [x] 银行/诊所/汇款处三大场所
- [x] Web Audio API 交互音效（点击/买/卖/事件/错误/场所/胜利/失败）
- [x] MP3 背景音乐（首页点击解锁，循环播放）
- [x] 交易页面背景动效（亮度脉冲 + CRT 扫描线）
- [x] 游戏结束清算页（资产统计/排行榜/老王评语）

## 部署到 GitHub Pages 的步骤

### 1. 创建 GitHub 仓库
```bash
cd cyber-fusheng-mvp
git init
gh repo create cyber-fusheng --public --source=. --push
```

### 2. 推送代码
```bash
git add .
git commit -m "init: 赛博浮生 MVP v1.0"
git push -u origin main
```

### 3. 开启 GitHub Pages
- 进入仓库 → Settings → Pages
- Source 选择 `Deploy from a branch`
- Branch 选择 `main`，目录选 `/ (root)`
- 保存后等待 1-2 分钟
- 访问地址: `https://<你的用户名>.github.io/cyber-fusheng/`

### 注意事项
- 所有资源路径使用相对路径（`./assets/...`），GitHub Pages 兼容
- MP3 文件约几 MB，GitHub 仓库大小限制 1GB，完全没问题
- 如需自定义域名，可在仓库根目录添加 `CNAME` 文件

## 待优化项（可选）
- [ ] 移动端适配（当前为桌面端布局）
- [ ] 更多商品和事件内容
- [ ] 排行榜接入在线 API（如 Firebase）
- [ ] 音效文件替换为更高质量的版本
- [ ] 分享功能（截图/生成分享卡片）
