![Build OpenWrt](https://github.com/amaumene/xiaomi_redmi-router-ac2100_openwrt_mesh/workflows/Build%20OpenWrt/badge.svg)
# Latest OpenWrt image for [Xiaomi Redmi AC2100](https://xiaomi-mi.com/wifi-routers/redmi-ac2100-router/) 802.11s enabled

This GitHub action is to build fresh images of latest OpenWrt snapshot using imagebuilder so I can automatically update my routers at home. 

As I have 3 routers with different roles, I generate an image for each kind.

What is common to all images:
 * add TCP BBR
 * removed all PPP packages
 * add luci
 * add 802.11s for mesh
 * add iperf3, mtr, iwinfo, libustream-wolfssl and ca-bundle

What is specific to type1:
* add wireguard (and luci-app-wireguard)
* add nextdns (and luci-app-nextdns)

What is specific to type2:
* add frps (and luci-app-frps)
* add shadowsocks-libev server (and luci-app-shadowsocks)
* add ttyd (and luci-app-ttyd)
* removed dnsmasq and odhcpd

What is specific to type3:
* removed dnsmasq and odhcpd

How do I use each image ?
* type1 is deployed on my router connected to internet.
* type2 is deployed on my router wired to type1, where I run frps, ttyd and shadowsocks.
* type3 is deployed on my router meshed to type1, and I only use it to extend my wifi network.

Feel free to use the image or the github action by forking it.

If you want to flash your router with latest type1:

```sysupgrade "https://github.com/amaumene/xiaomi_redmi-router-ac2100_openwrt_mesh/releases/latest/download/openwrt-ramips-mt7621-xiaomi_redmi-router-ac2100-squashfs-sysupgrade-type1.bin"```

If you want to flash your router with latest type2:

```sysupgrade "https://github.com/amaumene/xiaomi_redmi-router-ac2100_openwrt_mesh/releases/latest/download/openwrt-ramips-mt7621-xiaomi_redmi-router-ac2100-squashfs-sysupgrade-type2.bin"```

If you want to flash your router with latest type3:

```sysupgrade "https://github.com/amaumene/xiaomi_redmi-router-ac2100_openwrt_mesh/releases/latest/download/openwrt-ramips-mt7621-xiaomi_redmi-router-ac2100-squashfs-sysupgrade-type3.bin"```

/!\ Please note that I might change the packages included without notice. These images are built for my personnal use first.
