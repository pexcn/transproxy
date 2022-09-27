# Transproxy

A bridge of linux and transparent proxy.

## Usage

```sh
root@OpenWrt:~# transproxy --help
transproxy 0.2.11
A bridge of linux and transparent proxy.

USAGE:
    transproxy [OPTIONS]

OPTIONS:
    -t, --tcp-port       TCP transparent proxy port, support tproxy only.
    -u, --udp-port       UDP transparent proxy port, support tproxy only.
        --src-direct     Specify one or more source ip lists, outbound traffic from these ips
                         will be directly connected.
        --src-proxy      Specify one or more source ip lists, outbound traffic from these ips
                         will be pass through proxy.
        --src-normal     Specify one or more source ip lists, outbound traffic from these ips
                         will decide whether to pass through proxy according to the destination
                         ip lists.
        --dst-direct     Specify one or more destination ip lists, these ips will be directly
                         connected.
        --dst-proxy      Specify one or more destination ip lists, these ips will be pass
                         through proxy.
        --src-default    Default action for inbound traffic, available values: DIRECT, PROXY, NORMAL.
        --dst-default    Default action for outbound traffic, available values: DIRECT, PROXY.
        --self-proxy     Make local traffic pass through proxy, default as gateway only.
    -s, --server         Specify one or more ip addresses of the remote server, local and server
                         traffic will be directly connected.
    -i, --interface      Apply to specified network interface.
    -e, --extra          The specified parameters will be append to iptables.
    -m, --mark           Bypass outbound traffic with SO_MARK as specified value, it's a workaround
                         when the remote server doesn't have a static ip address.
                         [NOTE]: Not all clients support setting SO_MARK, and there may be
                         performance issues.
    -v, --verbose        Enable verbose logging.
    -f, --flush          Flush transproxy rules then exit.
    -h, --help           Show this help message then exit.
```

## Ports

- [x] [OpenWrt version](https://github.com/pexcn/openwrt-transproxy)
- [x] [Docker version](https://github.com/pexcn/docker-images/tree/master/utils/transproxy)

## Credits

It's just a parody of the big guy's work, the design idea was derived from ss-rules by [Jian Chang](mailto:aa65535@live.com) and [Yousong Zhou](mailto:yszhou4tech@gmail.com), thanks for their outstanding contribution to [FREEDOM](https://en.wikipedia.org/wiki/Liberty)!

- [@shadowsocks/luci-app-shadowsocks](https://github.com/shadowsocks/luci-app-shadowsocks)
- [@openwrt/packages/net/shadowsocks-libev](https://github.com/openwrt/packages/blob/master/net/shadowsocks-libev)

## License

```txt
Copyright (C) 2021-2022, Sing Yu Chan <i@pexcn.me>

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see <http://www.gnu.org/licenses/>.
```
