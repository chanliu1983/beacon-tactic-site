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

They were captured by two scripts in the game repository:

```
godot --path . res://tests/store_shot.tscn      # 01-03, the three battle scenes
godot --path . res://tests/marketing_shot.tscn  # 04-08, the menu and lobby screens
godot --path . res://tests/store_shot.tscn -- --clean   # 01-03 again, HUD hidden
```

The three clean images in `../screenshots/` are the `--clean` output, and
`../assets/` holds the web-page copies of every shot as 1600 × 1000 JPEG.

Two details worth keeping if they are ever re-shot:

* **Both scripts render at the native 2880 × 1800.** The older menu captures
  were pinned to 1600 × 900 and upscaled, and they were visibly soft next to
  the battle shots. Nothing pins the window size now.
* **`07_main_menu` has its dev footer blanked.** The menu's bottom-right line
  reads `v0.2.0 · mp17 · LAN build` in a LAN or Early Access build — honest
  there, but a store shot naming the protocol tag dates the whole set at the
  next `mp` bump, so `marketing_shot.gd` clears it just before the capture.

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

由游戏仓库里的两个脚本生成：

```
godot --path . res://tests/store_shot.tscn      # 01-03，三张战斗图
godot --path . res://tests/marketing_shot.tscn  # 04-08，主菜单与房间
godot --path . res://tests/store_shot.tscn -- --clean   # 01-03 再拍一次，无 HUD
```

`../screenshots/` 里的三张是 `--clean` 的产物；`../assets/` 是网页用的压缩版
（1600 × 1000 JPEG）。

重拍时有两点要留意：

* **两个脚本都按原生 2880 × 1800 渲染。** 早先几张界面图锁在 1600 × 900 再放大，
  和战斗图并排看明显发虚；现在不再锁窗口尺寸。
* **`07_main_menu` 的开发版页脚被清空了。** 主菜单右下角在局域网/抢先体验版本里
  写着 `v0.2.0 · mp17 · LAN build` —— 在那里是如实标注，但商店图上标出协议版本号，
  下次 `mp` 一动整套图就过时了，所以 `marketing_shot.gd` 在截图前把它清掉。
