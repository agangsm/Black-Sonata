# Black Sonata V1

English | [中文说明](#黑色奏鸣曲-v1)

A single-player browser-based virtual tabletop adaptation of the Black Sonata base game.

The project prioritizes the physical board-game experience. Players observe, track, place tokens, and make deductions themselves, while the application manages decks, hidden information, legal actions, Fog, Countdown, Search, Confront, and scoring. It does not automatically solve the mystery, calculate probabilities, eliminate candidates, or track the Lady's route.

## Features

- Complete single-player flow for the base game
- Official-style board, Stealth cards, Fog cards, Location Keys, Lady cards, and characteristic tokens
- Authentic Stealth Deck routes and hidden-movement logic
- Physical card-flip Search presentation using Stealth cards and Location Keys
- Clue reveals, reserved bonus clue, characteristic deduction, and Confront resolution
- Multiple game difficulties, Stealth sequence difficulties, and movement patterns
- Fog actions, Countdown handling, and Historian's Score
- English and Simplified Chinese interfaces
- Embedded official English rulebook, opened in a separate browser tab
- Fully offline, self-contained single-HTML release
- Separate developer tools for rule verification and layout calibration without exposing hidden information in the player interface

## Direct Use

### Static Web Version

The repository root contains the built static website:

```text
index.html
assets/
```

Deploy the repository to any static web host. GitHub Pages can use the root of the `main` branch as its publishing source.

### Standalone Offline Version

Open the following directory:

```text
Black-Sonata-rlease/
```

Download and open:

```text
Black-Sonata.html
```

The standalone HTML embeds the application, styles, images, rulebook, and LXGW WenKai font. It requires no Node.js installation, locally installed font, internet connection, or adjacent asset directory.

A recent version of Chrome, Edge, or another modern browser with WebP and WOFF2 support is recommended.

## Local Development

### Previewing This Release Repository

This repository is a prebuilt static release and does not require dependency installation or compilation. To avoid browser restrictions on local resources, start any static file server from the repository root, for example:

```powershell
python -m http.server 8000
```

Then visit `http://127.0.0.1:8000/`.

You can also open `Black-Sonata-rlease/Black-Sonata.html` directly to test the self-contained offline edition.

### Modifying and Rebuilding the Game

The complete development project uses React, Vite, and Node.js 20+. From a source checkout containing `app/package.json`, run:

```powershell
cd app
npm install
npm run dev
```

Common commands:

```powershell
npm run build
npm run build:single
npm run test:single-font
npm run verify:keyholes
```

- `npm run build`: builds the regular multi-file static version
- `npm run build:single`: builds the standalone offline HTML
- `npm run test:single-font`: verifies offline resources and the embedded font
- `npm run verify:keyholes`: verifies the physical Stealth-card and Location-Key overlap matrix

> This GitHub directory is primarily a distribution repository and does not contain the complete `app/` development source. Run the build commands from the full source project.

## Directory Structure

```text
Black-Sonata/
├─ index.html                    # Static web entry point
├─ assets/                       # Scripts, styles, and game assets
├─ fonts/                        # Original LXGW WenKai TTF archive
│  ├─ LXGWWenKai-Light.ttf
│  ├─ LXGWWenKai-Medium.ttf
│  └─ LXGWWenKai-Regular.ttf
├─ Black-Sonata-rlease/
│  ├─ Black-Sonata.html          # Self-contained offline edition
│  └─ fonts/
│     ├─ LXGWWenKai-Regular.woff2
│     └─ OFL.txt                 # LXGW WenKai font license
└─ README.md
```

`Black-Sonata-rlease/fonts/` preserves the font source and license for auditing and redistribution. The standalone HTML already embeds the WOFF2 font and does not read this directory at runtime.

## Disclaimer

This unofficial browser adaptation and Chinese localization are provided solely for board-game study, rules research, and non-commercial exchange. Commercial use is strictly prohibited.

The Black Sonata name, rules, artwork, board, cards, and other original components remain the property of their respective creators, publishers, and Side Room Games. This repository is not an official release and is neither affiliated with nor endorsed by Side Room Games.

If you enjoy the game, please support the official physical edition: [Black Sonata official page](https://www.sideroomgames.com/black-sonata/).

The implementation is based on:

- `Black_Sonata_rules_v20210104.pdf`: 2021 / 3rd printing rules
- `Black_Sonata_PnP_v20181112.pdf`: 2018 official PnP components

## Open-Source Licenses

This repository contains material with different licensing scopes:

- **LXGW WenKai** is used and redistributed under the [SIL Open Font License 1.1](./Black-Sonata-rlease/fonts/OFL.txt).
- **Third-party open-source software** remains subject to its respective license.
- **Original Black Sonata assets** are excluded from any open-source grant and remain copyrighted by their respective rights holders.
- **This web implementation and localization** are not automatically licensed for copying, modification, redistribution, or commercial use unless the repository provides an explicit `LICENSE` file.

Open-source software licenses do not alter the copyright status of the original board-game assets or grant permission for their commercial use.

---

# 黑色奏鸣曲 V1

[English](#black-sonata-v1) | 中文说明

《Black Sonata》基础游戏的单人浏览器虚拟桌面版本。

本项目以忠实还原实体桌游体验为目标：玩家自行观察、追踪、放置标记并完成推理；程序负责牌堆、隐藏信息、合法动作、迷雾、倒计时、搜索、对质与最终结算，不提供自动求解、概率提示、候选自动排除或黑夫人路线追踪。

## 功能

- 完整的基础游戏单人流程
- 基于官方组件的地图、潜行牌、迷雾牌、地点钥匙、黑夫人牌与特征标记
- 真实潜行牌路线与隐藏移动机制
- 地点钥匙与潜行牌的实体翻面搜索表现
- 线索揭示、奖励线索、特征推理与对质判定
- 多档游戏难度、潜行序列难度与移动规律
- 迷雾行动、倒计时与历史学家评分
- 中英文界面切换
- 内置官方英文规则书，可在浏览器新标签页中打开
- 支持完全离线运行的单文件版本
- 开发版本保留独立的规则验证与布局校准工具，正式玩家界面不会显示隐藏信息

## 直接使用

### 在线静态版

仓库根目录已经包含构建后的网页：

```text
index.html
assets/
```

将仓库部署到任意静态网页服务后即可使用。GitHub Pages 可直接将 `main` 分支根目录作为发布来源。

### 单文件离线版

进入以下目录：

```text
Black-Sonata-rlease/
```

下载并双击：

```text
Black-Sonata.html
```

该 HTML 已将游戏程序、样式、图片、规则书和 LXGW WenKai 字体内嵌到文件中。运行时不需要安装 Node.js、不需要安装字体、不需要联网，也不依赖旁置的 `assets/` 或 `fonts/` 目录。

建议使用最新版 Chrome、Edge 或其他支持现代 HTML、WebP 和 WOFF2 的浏览器。

## 本地开发

### 预览本仓库发布版

本仓库根目录是已经构建完成的静态发布目录，不需要安装依赖或重新编译。为避免浏览器对本地资源的访问限制，可在仓库根目录启动任意静态文件服务器，例如：

```powershell
python -m http.server 8000
```

然后访问 `http://127.0.0.1:8000/`。

也可以直接打开 `Black-Sonata-rlease/Black-Sonata.html`，测试完整的单文件离线版本。

### 修改和重新构建游戏

完整开发源码使用 React、Vite 与 Node.js 20+。在包含 `app/package.json` 的源码项目根目录执行：

```powershell
cd app
npm install
npm run dev
```

常用命令：

```powershell
npm run build
npm run build:single
npm run test:single-font
npm run verify:keyholes
```

- `npm run build`：生成普通多文件静态版本
- `npm run build:single`：生成可独立运行的单文件 HTML
- `npm run test:single-font`：验证单文件离线资源与内嵌字体
- `npm run verify:keyholes`：验证地点钥匙孔洞与潜行牌的物理命中关系

> 当前 GitHub 目录以成品发布为主，不包含完整的 `app/` 开发源码；上述构建命令应在完整源码项目中运行。

## 目录说明

```text
Black-Sonata/
├─ index.html                    # 在线静态版入口
├─ assets/                       # 在线静态版的脚本、样式与游戏素材
├─ fonts/                        # 原始 LXGW WenKai TTF 字体归档
│  ├─ LXGWWenKai-Light.ttf
│  ├─ LXGWWenKai-Medium.ttf
│  └─ LXGWWenKai-Regular.ttf
├─ Black-Sonata-rlease/
│  ├─ Black-Sonata.html          # 完整单文件离线版
│  └─ fonts/
│     ├─ LXGWWenKai-Regular.woff2
│     └─ OFL.txt                 # LXGW WenKai 字体许可证
└─ README.md
```

`Black-Sonata-rlease/fonts/` 用于保留字体来源和许可证，方便审计与再分发。单文件版已经内嵌 WOFF2 字体，不会在运行时读取该目录。

## 声明

本网页版及其汉化仅供桌游学习、规则研究与非商业交流，严禁用于任何商业用途。

《Black Sonata》的名称、规则、美术、地图、卡牌及其他原版组件版权归其原作者、出版方及 Side Room Games 所有。本仓库不是官方发行版本，也不代表或隶属于 Side Room Games。

如果你喜欢本作，请支持正版实体游戏：[Black Sonata 官方页面](https://www.sideroomgames.com/black-sonata/)。

本项目的规则与组件复现依据：

- `Black_Sonata_rules_v20210104.pdf`：2021 / 3rd printing 规则
- `Black_Sonata_PnP_v20181112.pdf`：2018 官方 PnP 组件

## 开源许可证

本仓库包含不同授权范围的内容：

- **LXGW WenKai / 霞鹜文楷**：依据 [SIL Open Font License 1.1](./Black-Sonata-rlease/fonts/OFL.txt) 使用与再分发。
- **第三方开源软件**：分别遵循其各自的开源许可证。
- **Black Sonata 原版素材**：不属于本项目的开源授权范围，版权归原权利人所有。
- **本项目网页实现与汉化内容**：除非仓库另行提供明确的 `LICENSE` 文件，否则不自动授予复制、修改、再发布或商业使用许可。

开源软件许可证不改变原版桌游素材的版权归属，也不构成对原版素材的商业使用授权。
