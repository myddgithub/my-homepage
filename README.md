# 陈玉东个人学术主页

站点：[soundspace.club](https://soundspace.club/)

内容：学术简介、研究平台、语音研究工具、详细简历与实验室模块介绍。

## 文件结构

```text
my-homepage/
├── index.html     # 单页主页，内含响应式样式与导航交互
├── myphoto.jpeg   # 个人照片
├── robots.txt    # 搜索引擎抓取说明
├── sitemap.xml   # 站点地图
├── LICENSE
└── README.md
```

网站为静态 HTML，无需构建。桌面版显示章节导航，手机和平板使用可展开菜单。
页面正文默认可见，JavaScript 用于菜单增强和入场动画；系统开启“减少动态效果”时不播放动画。

## 平台与工具访问

| 项目 | 入口与访问条件 |
| --- | --- |
| AI 中文语音教学 | Google Cloud 提供服务：[ai.soundspace.club](https://ai.soundspace.club/)，需使用管理员分发的账号登录 |
| Json2TG | [json2tg.soundspace.club](https://json2tg.soundspace.club/)，需访问凭据 |
| ToPics 韵律画图 | [topics.soundspace.club](https://topics.soundspace.club/)，需访问凭据 |
| 音视频转换与剪辑 | [公开源码](https://github.com/myddgithub/media-workbench-web)，支持本地部署；NAS 服务通过获授权的 Tailscale 通道访问，连接方式请联系咨询 |
| Speech Lab | [GitHub 私有仓库](https://github.com/myddgithub/speech-lab)，尚未公开，仅获授权用户可访问 |
| WhisperX-Me | 使用主页提供的 Tailscale HTTPS 入口，需连接获授权的 Tailscale 通道，服务主机保持开机且 WhisperX-Me 服务已启动；网页录音需允许浏览器使用麦克风，访问权限请联系咨询 |
| SoundSpace 语料平台 | [恢复原有平台入口](http://192.168.1.2:8000/)，需在同一局域网或使用可访问 NAS 局域网的 Tailscale 通道，并以管理员分发的账号登录 |
| mypy 脚本集合 | [GitHub 私有仓库](https://github.com/myddgithub/mypy)，需 GitHub 授权 |

本次核验中，`tg.soundspace.club` 实际指向 Json2TG，不能作为 WhisperX 的入口。
WhisperX-Me 已配置 Tailscale Serve，通过 HTTPS 入口代理至本机 `127.0.0.1:8766`，仅供获授权的 Tailscale 网络访问，不开放公网。原有 8766 端口的 HTTP 转发仍保留，但网页录音请使用 HTTPS 入口并授予麦克风权限。访问时需保持 Tailscale 与 WhisperX-Me 服务运行。
WhisperX-Me 的实际运行目录为 `D:\软件\WhisperX-Me-Web\WhisperX-Me-Web`，该目录包含便携版 Python runtime、模型和 FFmpeg；`D:\mypy\whisperx-me-web` 是对应的 GitHub 源码仓库，用于版本维护和重新打包。主页只通过 Tailscale HTTPS 地址访问运行中的部署目录，不直接调用源码仓库路径。
本仓库当前版本不再提供 ToPics 桌面版分卷安装包。

## 本地预览

在仓库根目录运行：

```bash
python -m http.server 8080 --bind 127.0.0.1
```

浏览器打开 [本地预览](http://127.0.0.1:8080/)。

## 部署与维护

WordPress 动态站已部署在搬瓦工，预览：

- https://phon.soundspace.club/
- https://www.soundspace.club/

后台 `/wp-admin/`。外观主题 `SoundSpace Academic` 沿用本仓库的 `index.html`。
apex `https://soundspace.club/` 在把 Cloudflare Pages 自定义域名改为指向 VPS 之前，仍是 Pages 静态站。

本仓库仍可作为主题源：改 HTML 后需同步到 VPS 主题目录 `/var/www/html/wp-content/themes/soundspace/`。日常改字、发文、统计在 WordPress 后台完成，不必每次 Git 部署。

更新内容时：

- 同步维护 `sitemap.xml` 的 `lastmod`。
- 以未登录访客身份检查公开链接和服务名称。
- 保留论文与科研项目的原生折叠交互，两处按钮文字均为“查看更多”。
- 检查桌面、平板和手机宽度，以及键盘菜单操作与减少动态效果设置。
- 学术署名、经历、论文数量及项目状态应依据原始资料更新。

## 联系

- 邮箱：[chenyd@cuc.edu.cn](mailto:chenyd@cuc.edu.cn)
- GitHub：[@myddgithub](https://github.com/myddgithub)

咨询平台访问时，请注明平台名称与用途。

## 许可

代码许可见 [LICENSE](./LICENSE)。头像仅供本站分发用途；第三方内容与依赖遵循各自许可。
