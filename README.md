# 留灯 LIUDENG

> 浙江　鹤溪村　海拔 680 米。山里给你留了一盏灯。

手机端竖屏滚动叙事恐怖民宿站。从山居、三间房、山中一日、住客的话，一路滚进巡夜点灯、58 只眼睛、族谱与退房终局。

## 在线访问

- **GitHub Pages**：https://liu233jh.github.io/liudeng/
- **CDN 备用**：https://aka.doubaocdn.com/s/QxyUJhk7x5

## 项目特点

- 零依赖单文件 `index.html`，不需要构建，也不需要服务器。
- 图片、字体、音频全部以 data URI 内嵌。
- 文件约 3.3MB，首次加载可能需要几秒；加载完成后不再请求外部素材。
- 手机端优先：视觉、滚动锁、触摸滑动均按 390×844 竖屏校准，同时保留桌面布局。

## 最近修复

- 眼睛段高度从 250vh / 220vh 缩为 100svh，移除 sticky 结束后的长黑尾。
- 族谱只在真正盖满屏幕后才隐藏眼睛层，避免族谱刚露头就留下上方空黑条。
- 族谱闪现改为整屏人脸：铺满屏、停留 1.55 秒后淡出，不再是 420px 小图或独立黑页。
- 人脸素材走单文件内嵌资源变量，CDN 版本不会因缺少 `img/` 目录而空白。
- 保留观看锁、58 只眼睛、退房终局、纸手、红门脸与“别划”面板。

## 目录

```text
.
├── index.html                    # 单文件站点（由 Actions 从已验证 CDN 源同步）
├── README.md
└── .github/workflows/deploy-pages.yml
```

## 本地预览

```bash
python3 -m http.server 8000
# 打开 http://127.0.0.1:8000/index.html
```

## 部署

仓库使用 GitHub Actions 发布 GitHub Pages：

1. 手动运行 `Deploy Liudeng to GitHub Pages`，或推送 `index.html` 触发。
2. 首次运行会从 CDN 拉取已验证的单文件版本，提交为 `index.html`，然后发布到 Pages。
3. 后续替换 `index.html` 并推送即可重新发布。

## 内容提示

页面包含闪烁、突然出现的人脸与恐怖音效；建议在安静、光线较暗的环境下观看。
