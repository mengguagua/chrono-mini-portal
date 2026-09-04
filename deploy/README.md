# 部署边界

- 当前项目：`chrono-mini-portal`，VPS 目录为 `/var/www/chrono-mini-portal`，域名为 `chrono-mini-portal.gaocc.cc`。
- 独立项目：VPS 目录 `/root/chrono-protal`。该目录属于另一个门户项目，不得在本项目部署中重命名、覆盖、迁移或删除。
- 本项目使用独立的发布包和 Nginx 站点配置。
- 公网入口沿用 `chrono.gaocc.cc` 的方式：Cloudflare Tunnel `chrono-protal-vps` 将 `chrono-mini-portal.gaocc.cc` 转发到 `http://127.0.0.1:8080`，Nginx 再按 Host 分流到本项目目录。
