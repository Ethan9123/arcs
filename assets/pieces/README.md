# 真实素材覆盖（自动探测，无需改代码）

默认棋盘用内嵌可染色 SVG 渲染棋子，离线零依赖、永不缺图。
若想换成真实图片（例如官方免费 Print-and-Play 切出的图），**只要把图片按下面命名放进对应目录即可**——
游戏启动时会自动探测哪些图片存在，存在即自动启用，缺图回退 SVG。**不需要改任何代码。**

## 放哪里、怎么命名

棋子 → 本目录 `assets/pieces/`：

```
ship_<color>.png        舰船
city_<color>.png        城市
starport_<color>.png    星港
```

`<color>` = `red` / `blue` / `yellow` / `white` / `imperial`（帝国舰）/ `free`（自由城市）

示例：`ship_red.png`、`city_blue.png`、`starport_yellow.png`、`ship_imperial.png`

资源 → `assets/resources/`：

```
material.png  物资
fuel.png      燃料
weapon.png    武器
relic.png     遗物
psionic.png   通灵
```

建议：透明背景、正方形、约 128×128 或更高；舰船/城市/星港图最好已是对应玩家颜色。

## 官方免费 Print-and-Play（合法素材来源）

Leder Games 官方资源页提供 Arcs 的免费 Print-and-Play（含 dice / ships / tokens / cards 的可打印件）：

- https://ledergames.com/pages/resources

下载后，从 PnP 的 token / ship 页里把对应图标裁切、按上面的文件名保存到这两个目录即可。
（素材版权归 Leder Games，仅供个人学习/测试，请勿商用或再分发。）

## 工作原理

`index.html` 启动时 `probeAssets()` 预探测约 20 个候选路径，加载成功的记入 `ASSET_OK` 并自动重渲染。
渲染时 `pieceArtSrc()` / `resArtSrc()` 优先用图片，缺图回退内嵌 SVG。
也可在 `index.html` 顶部 `PIECE_ART` 表显式指定路径（优先级最高）。
