# my-homepage

个人主页站点源码，线上地址：**[soundspace.club](https://soundspace.club/)**

> AI 助力，争分夺秒，让妄想日渐成真 · 坐标北京

---

## 在线一览

| 入口 | 说明 |
|------|------|
| [soundspace.club](https://soundspace.club/) | 本仓库静态主页 |
| [topics.soundspace.club](https://topics.soundspace.club/) | **ToPics 在线**（韵律出图 Web；需访问令牌） |
| [GitHub @myddgithub](https://github.com/myddgithub) | 代码与项目 |

---

## 仓库里有什么

```
my-homepage/
├── index.html          # 主页（头像、简介、链接、ToPics 入口）
├── myphoto.jpeg        # 头像
├── ToPics.7z.001–004   # 桌面版 ToPics 分卷下载（7-Zip 合并）
├── LICENSE
└── README.md
```

主页是单页 HTML：渐变背景 + 毛玻璃卡片，无需构建步骤。

### ToPics 桌面版下载说明

页面提供分卷包，下载后请用 **7-Zip** / **Bandizip** 等工具合并解压：

1. 将 `ToPics.7z.001` … `ToPics.7z.004` 放在同一目录  
2. 对 `ToPics.7z.001` 选择「解压」  
3. 运行解压出的 `ToPics.exe`（或新版 `ToPics_v2.exe`）

| 分卷 | 约大小 |
|------|--------|
| Part 1–3 | 各 20 MB |
| Part 4 | 约 8.3 MB |

源码与打包说明另见：

- 桌面：**[myddgithub/ToPics](https://github.com/myddgithub/ToPics)**  
- Web：**[myddgithub/topics-web](https://github.com/myddgithub/topics-web)**

### ToPics 在线

主页上的 **「打开 topics.soundspace.club」** 指向 Web 版韵律出图（波形 / 语图 / 共振峰 / 音高 / TextGrid）。

- 需要 **访问令牌**（`TOPICS_ACCESS_TOKEN`）  
- 服务通常由 NAS/本机经 **Cloudflare Tunnel** 对外提供  

---

## 本地预览

任意静态服务器即可，例如：

```bash
# Python
cd my-homepage
python -m http.server 8080
# 浏览器打开 http://127.0.0.1:8080/
```

或直接双击打开 `index.html`（部分浏览器对本地相对路径策略不同，推荐用本地 server）。

---

## 部署

当前对外域名：**https://soundspace.club/**

常见做法（任选其一）：

1. **Cloudflare Pages / 对象存储 + CDN**：绑定域名，根目录指向本仓库静态文件  
2. **GitHub Pages**：Settings → Pages → Deploy from branch `main` / `/`（若启用）  
3. **任意 Nginx / Caddy**：`root` 指向本目录，默认 `index.html`

修改主页后提交 `main`，按你现有流水线发布即可。

---

## 相关项目

| 仓库 | 角色 |
|------|------|
| [ToPics](https://github.com/myddgithub/ToPics) | 桌面批量韵律出图（v2） |
| [topics-web](https://github.com/myddgithub/topics-web) | ToPics Web MVP（Docker / Tunnel） |
| [nas-corpus-starter](https://github.com/myddgithub/nas-corpus-starter) | NAS 语料库平台 starter |

---

## 联系

- GitHub：[@myddgithub](https://github.com/myddgithub)  
- Email：[edwardcyd@gmail.com](mailto:edwardcyd@gmail.com)

---

## License

见 [LICENSE](./LICENSE)。头像与分卷安装包仅供本站分发用途；第三方依赖（如 parselmouth / ffmpeg）请遵守其各自许可。
