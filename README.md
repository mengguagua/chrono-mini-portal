# Chrono Mini 宣传官网

竖版战斗转轮微信小游戏「Chrono Mini」的单页营销站。

## 运行

```bash
# 方式一：直接打开
open index.html

# 方式二：本地服务器（推荐，资源路径更稳定）
python3 -m http.server 8311
# 浏览器访问 http://localhost:8311
```

## 设计

- **风格基底**：Raycast 式黑暗画布 + 1px 细线 + 单一强调色（Chrono 青蓝 `#3fd8c8`）
- **像素还原**：所有游戏截图 / 怪物图使用 `image-rendering: pixelated`，整数倍放大不糊
- **配色取自游戏**：背景暗色 `#07080a`、卡片 `#0d1114`、强调色与游戏 UI 青蓝 Cave 一脉相承
- **三主色系统**：
  - `chrono` 青蓝（科技/生命/能量）
  - `ember` 红（Boss/危险）
  - `gold` 金（升级/装备）
- **字体**：中文 PingFang / 微软雅黑 + 备选 ZCOOL 字体（已引入但未在线加载，离线时回落 sans）
- **叙事顺序**：Hero（slogan + 数据）→ 核心玩法（6 张卡片）→ 地下之旅（实机截图叙事）→ 怪物志（普通/镜像/Boss 卡片）→ 终局 CTA

## 文件结构

```
chrono-mini-protal/
├── index.html                  # 单文件站点（所有样式内联）
├── README.md
└── assets/
    ├── brand/avatar.png        # 品牌头像（favicon 也用它）
    ├── monsters/               # 怪物像素图（image-rendering: pixelated 渲染）
    └── screenshots/            # 游戏实机截图
```

## 资源来源

- 截图：`chrono-mini/screenshots/audit/`（Lv.05 Boss 战利品 / Lv.14 炽焰爆发 / 升级强化）
- 怪物：`chrono-mini/assets/monsters/{main, fungus}/` + 同人熔火幼龙
- 头像：`chrono-mini/marketing/wechat-mini-avatar-source-v2.png`

## 性能 / 兼容性

- 单文件 HTML，无外部依赖，无需构建
- 滚动淡入：`.rv` 元素 + IntersectionObserver（含 3s 兜底 timeout + `no-IO` 全亮回退）
- 响应式断点：920px / 640px 三档布局
- 兼容 iOS Safari 16+ / Chrome 110+ / 微信内置浏览器
