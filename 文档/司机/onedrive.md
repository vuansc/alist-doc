---
sidebar_position: 4
---

# OneDrive

:::tip
如果你的账号不支持API，（比如学校账号未验证管理员，或者是管理员禁用了API），那么你还可以通过webdav的方式来挂载。具体见 [webdav](webdav.md)
:::

### 视频教程

<!-- <iframe src="//player.bilibili.com/player.html?aid=636185928&bvid=BV1Rb4y1E7NV&cid=499811348&page=1&high_quality=1&danmaku=1&as_wide=1" scrolling="no" border="0" width="100%" height="500" frameborder="no" framespacing="0" allowfullscreen="true"> </iframe> -->
<video controls src="https://video-direct-link.vercel.app/bili.mp4?aid=636185928&bvid=BV1Rb4y1E7NV&cid=499811348" width="100%" />

[**https://www.bilibili.com/video/BV1Rb4y1E7NV**](https://www.bilibili.com/video/BV1Rb4y1E7NV)

### First

首先打开https://tool.nn.ci/onedrive/request

### 创建应用
> 你也可以选择跳过此步，使用默认提供的client，但是需要组织管理员批准。

- 在打开的页面，选择所在区域，点击创建应用
- 登陆后选择「注册应用程序」，输入「名称」，选择「任何组织目录中的账户和个人」（注意这里不要看位置选择而是看文字，部分人可能是中间那个选项，不要选成单一租户或者其他选项，否则会导致登陆时出现问题），输入重定向 URL 为 <https://tool.nn.ci/onedrive/callback> ，「注册」即可，然后可以得到client_id
  ![client_id](https://store.heytapimage.com/cdo-portal/feedback/202111/24/998aa05659a10e87b3f2161d844263f8.png)
- 注册好应用程序之后，选择「证书和密码」，点击「新客户端密码」，输入一串密码，选择时间为最长的那个，点击「添加」
  （注：在添加之后输入的密码之后会消失，请记录下来 client_secret 的值）
  ![client_secret](https://store.heytapimage.com/cdo-portal/feedback/202111/24/a3c7b8fd2a6577ee62404ad054ebbe90.png)
- 选择「API 权限」，点击 「MicroSoft Graph」，在「选择权限」中输入 file，勾选 「Files.read」（注：Files.read 是只读最小权限，图中权限较大，也同样可以），点击「确定」
  ![api](https://store.heytapimage.com/cdo-portal/feedback/202111/24/15cf3a64994935cdda76185cc181fad1.png)
### 获取刷新令牌
将上一步骤中获得的client_id和client_secret填入https://tool.nn.ci/onedrive/request 这个页面，点击获取刷新令牌，就可以得到刷新令牌了

### 获取Sharepoint site_id
如果需要挂载Sharepoint，完成上一步后，在显示刷新令牌的界面会出现一个输入站点地址，输入站点地址后点击获取site_id即可。
### 添加账号
将上述过程中获取得到的值依次填入即可。
#### 根目录路径
默认为`/`，如果需要自定义，就填路径就行，从根路径开始，和本地路径一样，比如`/test`
