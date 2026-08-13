摩鑫主管app【Q-——333307——】摩鑫主管app【 辋芷《888yx●vip》 】
摩鑫主管app【Q-——333307——】摩鑫主管app【 辋芷《888yx●vip》 】

 从零搭建个人博客：Github Pages + Hexo 完整教程

你是不是也想拥有一个属于自己的博客，却总被服务器、域名、备案劝退？别担心，Github Pages 免费托管 + Hexo 静态博客框架，是目前最流行的零成本建站方案。今天这份保姆级教程，手把手带你从零上线，全程无命令行恐惧，跟着做就能跑通。

 为什么选择 Github Pages + Hexo？

- 免费：托管在 Github 上，不花一分钱，没有服务器运维压力。
- 速度快：静态页面，CDN 加速，国内访问也很快。
- 灵活：想换主题就换，支持 Markdown 写作，专注内容本身。
- 版本管理：每次改动都有记录，写坏了还能一键回滚。

 第一步：准备环境

你需要两个东西：一个 Github 账号（没有就注册），以及一个本地代码编辑器（推荐 VS Code）。接着，安装 Node.js（建议 LTS 版本），这是 Hexo 的运行基础。

 第二步：安装 Hexo 并初始化博客

打开终端，全局安装 Hexo 脚手架：

```bash
npm install -g hexo-cli
```

然后在你的工作目录下初始化博客：

```bash
hexo init my-blog
cd my-blog
npm install
```

启动本地预览，看看初始效果：

```bash
hexo server
```

浏览器访问 `http://localhost:4000`，看到蓝色默认主题就成功了。

 第三步：配置站点信息

用编辑器打开 `_config.yml`，这是博客的全局配置。重点改这三个项：

- `title`：博客名称，建议包含“个人博客”或你的领域关键词。
- `author`：你的名字，用于文章署名。
- `url`：后面部署到 Github 后的正式域名，先留空。

完成后保存，刷新本地页面就能看到变化。

 第四步：写第一篇文章

清除默认示例

```bash
hexo clean
hexo new post "我的第一篇博客"
```

打开 `source/_posts/` 下的 Markdown 文件，写点内容。记得在头部添加 `tags` 和 `categories`，有助于 SEO 收录。

 第五步：部署到 Github Pages

在 Github 新建一个仓库，命名格式必须为：`你的用户名.github.io`。然后在终端安装部署插件：

```bash
npm install hexo-deployer-git --save
```

修改 `_config.yml` 末尾的 deploy 配置：

```yaml
deploy:
  type: git
  repo: https://github.com/你的用户名/你的用户名.github.io.git
  branch: main
```

最后执行：

```bash
hexo g && hexo d
```

几分钟后，访问 `https://你的用户名.github.io`，你的博客就正式上线了。

 额外提升：绑定自定义域名与 SEO 优化

想要更专业，可以在仓库 Settings 里绑定自己的域名。同时，安装 `hexo-generator-seo-friendly-sitemap` 插件，生成站点地图，提交到百度搜索资源平台，能加速收录。

如果本教程对你有一点点帮助，欢迎点赞、收藏，或者评论区告诉我你踩过的坑。你的每一次互动，都是我更文的最大动力。有问题也可以留言，我们下期见。

相关推荐：

https://github.com/gardnermatthew7446/fsiwef/blob/main/2027%E5%AE%98%E7%BD%91%E7%83%AD%E7%82%B9%EF%BC%9A%E6%91%A9%E8%87%A3%E5%AE%98%E6%96%B9%E7%BD%91%E7%AB%99_%E4%BA%A2%E5%87%A1%E9%95%81%E5%A4%B4%E8%82%9BFMNHH.md

<img src="https://i.postimg.cc/hvxs9bm3/moxin-00003.png" />

相关推荐：

https://github.com/gardnermatthew7446/fsiwef/commit/95fe2995ac4fda069e09a7cfcec35b6220a6d932

<img src="https://i.postimg.cc/wMJ2hcJg/moxin-00006.png" />
相关推荐：

https://github.com/halldiane96/dybugq/blob/main/2027%E7%A7%91%E6%8A%80%E8%A7%A3%E6%9E%90%EF%BC%9A%E6%91%A9%E8%87%A3%E5%AE%98%E6%96%B9%E6%B3%A8%E5%86%8C_%E8%B0%B1%E5%90%95%E8%B0%8B%E5%B0%98%E5%AF%A1DKRYZ.md

<img src="https://i.postimg.cc/hvxs9bm3/moxin-00003.png" />
相关推荐：

https://github.com/halldiane96/dybugq/commit/37d34380a137298763a85b14537b9261e9a4bc1b

<img src="https://i.postimg.cc/wMJ2hcJg/moxin-00006.png" />

资讯来源：新华网、人民网、央视新闻、中新网、凤凰网、澎湃新闻、界面新闻、新浪新闻、搜狐网、财新网、观察者网、第一财经等主流平台，以独树一帜的观察视角与扎实的深度报道能力，在资讯领域收获广泛关注。
