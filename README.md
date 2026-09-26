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
| 音视频转换与剪辑 | [公开源码](https://github.com/myddgithub/media-workbench-web)，按项目文档部署 |
| Speech Lab | [GitHub 私有仓库](https://github.com/myddgithub/speech-lab)，尚未公开，仅获授权用户可访问 |
| WhisperX-Me | 个人电脑部署；需主机开机并启动服务，通过 Tailscale 等工具共享使用，连接方式请联系咨询 |
| SoundSpace 语料平台 | 私有 NAS 部署；需连接 Tailscale，并使用管理员分发的账号登录 |

本次核验中，`tg.soundspace.club` 实际指向 Json2TG，不能作为 WhisperX 的入口。
本仓库当前版本不再提供 ToPics 桌面版分卷安装包。

## 本地预览

在仓库根目录运行：

```bash
python -m http.server 8080 --bind 127.0.0.1
```

浏览器打开 [本地预览](http://127.0.0.1:8080/)。

## 部署与维护

现有站点使用 Cloudflare Pages 的 Git 集成。将审核后的修改推送到本仓库
`main` 分支会触发部署；在提交检查中确认 “Cloudflare Pages” 成功后，
再核对 [正式站点](https://soundspace.club/) 的实际内容。

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
