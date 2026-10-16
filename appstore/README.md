# App Store screenshots

The eight screenshots submitted to App Store Connect, in four pixel sizes.
Every set is 16:10 PNG and shows the same eight scenes in the same order, so
picking one set changes nothing but the resolution.

中文说明见文末。

## Sets

| Folder | Size | Notes |
|---|---|---|
| `2880x1800/` | 2880 × 1800 | The game's native window size (maximised on a 1440 × 900 @2x display). Start here. |
| `2560x1600/` | 2560 × 1600 | Same aspect, smaller file. |
| `1440x900/` | 1440 × 900 | The same image at 1x on a 1440 × 900 display. |
| `1280x800/` | 1280 × 800 | The smallest set. |

`CONTACT_SHEET.png` is not an App Store asset — it is all eight scenes on one
sheet, for review and for picking an order.

## Order

The numbers are the order to upload them in. The first one is the storefront
tile, so it is the one worth optimising:

1. `01_battlefield` — a live exchange on the built-up ridge
2. `02_storm` — the storm turn closing in
3. `03_beacon_disc` — a planted beacon and its territory ring
4. `04_crew_select` — picking a crew before a match
5. `05_training_hall` — the four-room training hall
6. `06_tactics_map` — the tactics map
7. `07_main_menu` — the main menu
8. `08_lobby_4v4` — a four-on-four lobby

## How they were made

Rendered from the real game, not mocked up: a fixed `world_seed = 20261016`,
the game's own rules placing the beacons, explosions, voxels and guards, then
each scene framed and frozen. The seed matters — re-rendering without it
produces a different map and these no longer match each other.

They were captured by `tests/store_shot.gd` in the game repository. Re-run with:

```
godot --path . res://tests/store_shot.tscn          # with the in-game HUD
godot --path . res://tests/store_shot.tscn -- --clean   # HUD hidden
```

The three clean images in `../screenshots/` are the `--clean` output.

---

# 中文说明

提交 App Store Connect 用的八张截图，四种像素尺寸。每个尺寸都是 16:10 的 PNG，
八张图内容与顺序完全一致 —— 换尺寸只改分辨率，不改画面。

| 目录 | 尺寸 | 说明 |
|---|---|---|
| `2880x1800/` | 2880 × 1800 | 游戏窗口的原生尺寸（1440 × 900 @2x 屏幕全屏时的输出）。建议优先用这一套。 |
| `2560x1600/` | 2560 × 1600 | 同样比例，体积更小。 |
| `1440x900/` | 1440 × 900 | 1440 × 900 屏幕 1x 下的同一张图。 |
| `1280x800/` | 1280 × 800 | 最小的一套。 |

`CONTACT_SHEET.png` 不是上架素材，是八张图拼在一张上的总览图，方便挑选顺序。

## 顺序

文件名里的编号就是上传顺序。第一张是商店列表里显示的缩略图，最值得花时间打磨：

1. `01_battlefield` —— 已经建起工事的山脊上的交火
2. `02_storm` —— 风暴回合逼近
3. `03_beacon_disc` —— 已点亮的信标与它的作用圈
4. `04_crew_select` —— 开局前选队伍
5. `05_training_hall` —— 四房间训练大厅
6. `06_tactics_map` —— 战术地图
7. `07_main_menu` —— 主菜单
8. `08_lobby_4v4` —— 四对四房间

## 是怎么拍出来的

不是拼贴，是真机渲染：固定 `world_seed = 20261016`，用游戏自己的规则放信标、
制造爆炸、堆体素和守卫，然后逐张取景冻结。种子是关键 —— 不固定它重拍出来的
地图就不一样，这八张图也就对不上了。

由游戏仓库里的 `tests/store_shot.gd` 生成，重拍命令见上。
`../screenshots/` 里的三张是无 HUD 版本（`--clean`）。
