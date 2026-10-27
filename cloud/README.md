# math-kingdom-cloud

「数学王国大冒险 · 口算闯关」的云端静态资源仓库。通过 jsDelivr CDN 供网页版 / 微信小程序按需加载，减小首包体积。

## 目录结构

```
cloud/
├── skins/       付费角色皮肤立绘（6 款，绘本风 SVG）
├── wardrobe/    付费/奖励装备图（7 件，绘本风 SVG）
└── activities/  节日活动配置（JSON，后台可配，改文件即上新活动，无需发版）
```

## CDN 地址

游戏 `config.js` 中 `MK.CLOUD.base` 配置为：

```
https://cdn.jsdelivr.net/gh/HZQaaaaaa/math-kingdom-cloud@main
```

资源 URL = base + 相对路径 + `?v=<MK.CLOUD.version>`。

## 更新资源（无发版）

1. 替换 `cloud/` 下对应文件并 push 到 main 分支；
2. 把游戏 `config.js` 中 `MK.CLOUD.version` +1（强制客户端绕过 CDN 缓存重新拉取）；
3. 刷新游戏即可生效。

> 注意：jsDelivr 默认对 `@main` 缓存约 12 小时，改版本号即可穿透缓存。私有仓库不会被 CDN 服务，本仓库保持公开。
