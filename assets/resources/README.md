# 资源真实素材（自动探测，无需改代码）

把资源 token 图片按下面命名放进本目录 `assets/resources/`，游戏启动会自动探测并启用；缺图回退内嵌 SVG。

```
material.png  物资
fuel.png      燃料
weapon.png    武器
relic.png     遗物
psionic.png   通灵
```

建议透明背景、正方形（约 128×128 或更高）。

## 当前已放入（2026-06-24）
本目录已放入 5 张资源 token（material/fuel/weapon/relic/psionic.png，160×160 圆形透明 PNG），
取自本机 TTS 汉化模组（Steam Workshop 3418190840，D_T 汉化）缓存里的资源贴图
（`Custom_Tile` 的 r-*.jpg，圆形 token 面），经圆形 alpha 蒙版+降采样处理而成。
游戏启动 `probeAssets()` 自动探测启用——玩家面板资源条/规则速查图例已显示为真实 token。

> 调研结论：该 TTS 模组里**只有资源是平面 token 贴图**可直接用；城市/星港是同一张 `Custom_Token`
> 贴图（按对象上色，无法区分类型/阵营），舰船/密探/旗舰均为 3D 模型（.obj），都没有可用的俯视平面图，
> 故棋盘上的舰船/建筑仍用既有的「可染色原创 SVG」最合适。

## ⚠️ 版权边界
这些资源 token 源自 Leder Games《Arcs》（经汉化模组再加工），版权归 Leder Games。
**仅放在本地个人副本使用**；本项目约定不把 Leder 位图美术提交/部署到公开仓库（GitHub Pages = 再分发）。
缺图时自动回退到内嵌原创 SVG，公开线上版即用 SVG，不含这些位图。

合法的公开替代来源：Leder Games 官方免费 Print-and-Play（https://ledergames.com/pages/resources）。

详见上级目录 `assets/pieces/README.md` 的完整说明。
