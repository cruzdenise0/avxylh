V8地址登录【Q-——333307——】V8地址登录【 辋芷《888yx●vip》 】
V8地址登录【Q-——333307——】V8地址登录【 辋芷《888yx●vip》 】

 如何用 GitHub Actions 自动构建 Docker 镜像并推送到阿里云 ACR

最近在部署个人项目时，频繁手动构建镜像、推送仓库，效率极低。如果你也遇到同样问题，强烈建议试试 GitHub Actions 搭配 阿里云容器镜像服务 ACR，实现全自动 CI/CD 流水线，推送一次代码，镜像自动构建并更新。

 为什么选择 GitHub Actions + 阿里云 ACR？

- 零成本启动：GitHub Actions 对公共仓库完全免费，私有仓库月免费额度也够个人使用。
- 原生关联：修改代码后自动触发，无需安装额外插件。
- 国内外拉取速度快：阿里云 ACR 在国内有多个区域镜像加速，适合部署到国内服务器。

 配置步骤

在仓库根目录创建 `.github/workflows/deploy.yml` 文件，内容如下（核心部分）：

```yaml
name: 自动构建镜像并推送至阿里云 ACR

on:
  push:
    branches: [ main ]

jobs:
  build-and-push:
    runs-on: ubuntu-latest
    steps:
    - name: 拉取代码
      uses: actions/checkout@v2

    - name: 登录阿里云ACR
      uses: docker/login-action@v1
      with:
        registry: registry.cn-hangzhou.aliyuncs.com
        username: ${{ secrets.ACR_USERNAME }}
        password: ${{ secrets.ACR_PASSWORD }}

    - name: 构建并推送
      uses: docker/build-push-action@v2
      with:
        context: .
        push: true
        tags: registry.cn-hangzhou.aliyuncs.com/你的命名空间/你的镜像名:latest
```

 关键点提醒

1. 设置 Secrets：在 GitHub 仓库 `Settings -> Secrets` 中添加 `ACR_USERNAME` 和 `ACR_PASSWORD`，切勿明文写在代码中。
2. 触发器控制：`on.push.branches` 可改为 `tags` 监听版本号发布，适合生产环境每次发布新版本。
3. 构建缓存：可添加 `cache-from` 参数加速二次构建，节省大量时间。

> 疑问：如果你需要构建多平台（如 ARM + x86）镜像怎么办？可以在 `build-push-action` 中增加 `platforms: linux/amd64,linux/arm64`，配合 QEMU 实现跨平台打包。

 效果验证

推送代码后，进入仓库的 `Actions` 页面即可看到工作流运行日志。构建成功后，登录阿里云控制台，确认仓库中新镜像的更新时间是否更新。

这套流程适合个人博客、API 服务、定时任务等场景。你正在处理什么项目？欢迎在评论区分享你的部署痛点，我会根据反馈输出更细的解决方案。 别忘了点赞收藏，下次部署时能快速找到这篇教程。如果希望看到更多关于 Nginx 反代、K8s 滚动更新的内容，也在评论区告诉我，关注我，持续分享开发运维干货。

相关推荐：

https://github.com/hamiltonlinda25/thgubw/blob/main/2026%E5%AE%98%E6%96%B9%E6%B1%87%E6%80%BB%EF%BC%9AV8%E5%9C%B0%E5%9D%80app_%E6%8F%AD%E6%AE%96%E8%BF%90%E8%9B%94%E5%9C%B0FSNSN.md

<img src="https://i.postimg.cc/J7sVTRgT/V8-00010.png" />

相关推荐：

https://github.com/hamiltonlinda25/thgubw/commit/a607f868b1038144e4af74721427cb5fd80d3b4e

<img src="https://i.postimg.cc/5tbnDmt0/V8-00001.png" />
相关推荐：

https://github.com/davisgina32/bajxxs/blob/main/%E5%BD%B1%E8%A7%86%E5%9C%88%E6%96%B0%E5%8A%A8%E5%90%91%EF%BC%9AV8%E5%9C%B0%E5%9D%80%E4%B8%BB%E7%AE%A1_%E6%AD%89%E4%BF%A3%E9%B8%A6%E8%A3%99%E9%80%94KLFTN.md

<img src="https://i.postimg.cc/tJZ5FSB6/V8-00007.png" />
相关推荐：

https://github.com/davisgina32/bajxxs/commit/f8ea8ac9cfdeb0034c1cc6b8075a71a5747ef6a2

<img src="https://i.postimg.cc/2ysxGQJ5/V8-00009.png" />

资讯来源：新华网、人民网、央视新闻、中新网、凤凰网、澎湃新闻、界面新闻、新浪新闻、搜狐网、财新网、观察者网、第一财经等主流平台，以独树一帜的观察视角与扎实的深度报道能力，在资讯领域收获广泛关注。
