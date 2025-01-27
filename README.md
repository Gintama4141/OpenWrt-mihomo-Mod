![GitHub License](https://img.shields.io/github/license/morytyann/OpenWrt-mihomo?style=for-the-badge&logo=github) 
![GitHub Tag](https://img.shields.io/github/v/release/rizkikotet-dev/OpenWrt-mihomo-Mod?style=for-the-badge&logo=github) 
![GitHub Downloads (all assets, all releases)](https://img.shields.io/github/downloads/rizkikotet-dev/OpenWrt-mihomo-Mod/total?style=for-the-badge&logo=github) 
![GitHub Repo stars](https://img.shields.io/github/stars/rizkikotet-dev/OpenWrt-mihomo-Mod?style=for-the-badge&logo=github) 
[![Telegram](https://img.shields.io/badge/Contact-Telegram-26A5E4?style=for-the-badge&logo=telegram)](https://t.me/RizkiKotet)

# MihomoTProxy-MOD

Transparent Proxy with Mihomo on OpenWrt.

## Prerequisites

- OpenWrt >= 23.05
- Linux Kernel >= 5.10
- firewall4

## Feature

- Transparent Proxy (TPROXY/TUN, IPv4 and/or IPv6)
- Access Control
- Profile Mixin
- Profile Editor
- Scheduled Restart

## Install & Update

### Use Auto Script (Recommended)

```shell
bash -c "$(wget -qO - 'https://github.com/rizkikotet-dev/OpenWrt-mihomo-Mod/raw/refs/heads/main/autoscript.sh')"
```

## How To Use

See [Wiki](https://github.com/morytyann/OpenWrt-mihomo/wiki)

## How does it work

1. Mixin and Update profile.
2. Run mihomo.
3. Run hijack prepare script.
4. Set router hijack.
5. Set lan hijack with access control.
6. Set scheduled restart.

Note that the steps above may change base on config.

## Compilation

```shell
# add feed
echo "src-git mihomo https://github.com/rizkikotet-dev/OpenWrt-mihomo-Mod;main" >> "feeds.conf.default"
# update & install feeds
./scripts/feeds update -a
./scripts/feeds install -a
# make package
make package/luci-app-mihomo/compile
```

The ipk file will be found under `bin/packages/your_architecture/mihomo`.

## Dependencies

- ca-bundle
- curl
- yq
- firewall4
- ip-full
- kmod-inet-diag
- kmod-nft-tproxy
- kmod-tun

## Special Thanks

- [@pmkol](https://github.com/pmkol)
- [@ApoisL](https://github.com/vernlau)
- [@xishang0128](https://github.com/xishang0128)
