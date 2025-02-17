# iptv-sources

Autoupdate iptv sources

[![Docker Build](https://img.shields.io/docker/automated/herberthe0229/iptv-sources?style=flat-square)](https://hub.docker.com/r/herberthe0229/iptv-sources)
[![Docker Version](https://img.shields.io/docker/v/herberthe0229/iptv-sources?style=flat-square)](https://hub.docker.com/r/herberthe0229/iptv-sources)
[![Docker Image](https://img.shields.io/docker/image-size/herberthe0229/iptv-sources/latest?style=flat-square)](https://hub.docker.com/r/herberthe0229/iptv-sources)
[![Docker Pulls](https://img.shields.io/docker/pulls/herberthe0229/iptv-sources?style=flat-square)](https://hub.docker.com/r/herberthe0229/iptv-sources)
[![Docker Stars](https://img.shields.io/docker/stars/herberthe0229/iptv-sources?style=flat-square)](https://hub.docker.com/r/herberthe0229/iptv-sources)

Join discord: [![Discord](https://discord.badge.ibert.me/api/server/betxHcsTqa)](https://discord.gg/betxHcsTqa)

Sources are from:

- <https://epg.pw/test_channel_page.html>
- [iptv.org](https://github.com/iptv-org/iptv)
- [YueChan/Live](https://github.com/YueChan/Live)
- [YanG-1989/m3u](https://github.com/YanG-1989/m3u)
- [fanmingming/live](https://github.com/fanmingming/live)

See <https://m3u.ibert.me> to get more.

> Use CDN **(Not recommended)**: You can use `https://fastly.jsdelivr.net/gh/HerbertHe/iptv-sources@gh-pages/` to replace `https://m3u.ibert.me/` for using CDN Service. Due to the **Cache Policy** of CDN, the content wouldn't be the latest, the m3u files would be updated every **3 hours**.

> 使用 CDN **（不建议）**：你可以通过 `https://fastly.jsdelivr.net/gh/HerbertHe/iptv-sources@gh-pages/` 替换 `https://m3u.ibert.me/` 来使用 CDN 服务。由于 CDN 的 **缓存策略**，内容不会是最新的，m3u 文件每 **3 小时** 会更新一次。

## Deploy by yourself

You can also deploy the project by yourself with docker.

```bash
docker run --name iptv-sources -p 3000:8080 -d herberthe0229/iptv-sources:latest
```

- Run `docker ps` to get container status.

Wait a minute, visit <http://localhost:3000>.

Then, you can use `http://localhost:3000` instead of `https://m3u.ibert.me`.

For example: `https://m3u.ibert.me/cn.m3u` -> `http://localhost:3000/cn.m3u`

Or, you can also deploy with your own server & domain.

## Crontab

Maybe you want to set schedule for auto-updating per 2 hours.

- Download bash script file `iptv-sources.sh` <https://github.com/HerbertHe/iptv-sources/blob/main/iptv-sources.sh> to your homedir.

- Edit you crontab:

```bash
crontab -e
```

- Press keyboard `i` for adding schedule.

- Add:

```cron
0 */2 * * * /bin/sh ~/iptv-sources.sh
```

- Press keyboard `ESC` to exit edit mode
- Type `:wq` to save
- Restart crontab service

```bash
service crond restart
```

## LICENSE

MIT &copy; Herbert He 2023
