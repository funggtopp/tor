<font color=red> 自用的，主要是用来上上谷歌邮箱，在油管上骂骂汉奸之类</font> <br>
Tor will creat LISTEN port at 127.0.0.1:9050.<br>
You can modify it in torrc<br>
## gwflist.pac
用于脚本代理时使用。<br>
日本：https://fastly.jsdelivr.net/gh/funggtopp/tor@main/gfwlistforsquid.pac<br>
韩国：https://ghproxy.com/https://raw.githubusercontent.com/funggtopp/tor/main/gfwlistforsquid.pac<br>
加速：https://raw.gitmirror.com/funggtopp/tor/main/gfwlistforsquid.pac<br>
## linux tor
you should use <code>tor -f torrc</code> to run your tor.

## torrc
torrc is a very important file,especially if you are in ...
Your torrc maybe like this:

```
#SocksPort 0.0.0.0:9050
#HTTPSProxy 127.0.0.1:8787
#Socks5Proxy 127.0.0.1:1080
#DNSPort 127.0.0.1:9053

UseBridges 1
#UpdateBridgesFromAuthority 1
DataDirectory ./Data
GeoIPFile ./Data/geoip
GeoIPv6File ./Data/geoip6
#Log notice file ./Data/tor.log
AvoidDiskWrites 1

ExitNodes {de},{fr},{nl},{ch},{dk}
StrictExitNodes 1
ExcludeNodes {jp},{kr},{cn},{hk},{mo},{sg},{th},{pk},{by},{ru},{ir},{vn},{ph},{my},{cu}

#for windows
ClientTransportPlugin obfs4 exec ./PluggableTransports/obfs4proxy.exe
#for linux
#ClientTransportPlugin obfs4 exec ./obfs4proxy managed

Bridge obfs4 87.62.98.157:9351 2BD90810282F8B331FC7D47705167166253E1442 cert=B1xiK/dAFZPOJ0aeo0qrajIUiB3B2q1HAT2j2I5h+GWeQArJi904IM3+DPIdc/VwM1jlMg iat-mode=0
Bridge obfs4 185.163.46.63:443 60728A289529B2A0819BC7DC7A73A780567B73C8 cert=xNfHXSkbUcJDlLOsZ3wM6swwI1LIvRgySKJdY4liYbOVCdBVKPErgVSav2DPfGzN1ZpxJQ iat-mode=0
Bridge obfs4 195.201.14.15:37361 3BECEABD174AE41C5CCC17254A40DD24EC5372CD cert=vlSA6qJIck/UH66T/2yoMtE44lbIEJ9fLCpwUl5ffGWBT6gUYU62sQLz9EIv5DrbROm1Og iat-mode=0
Bridge obfs4 80.209.236.183:443 0875F92379ACA7CC3ADB3FC176338B28EF307161 cert=gcWOwepy4SUWha+KBYDOYAv6Kqyf2L52ehHG/Nq7vryLcPEqU5B0776CzI+BuyUzY7JqFg iat-mode=0
Bridge obfs4 176.123.5.206:8847 23A1030BDC7C8DCCE58A1685B1521AF35E87A0D9 cert=ghLa7M2BFsY6rvgBE7WnDUoFv/bghTmE3plzGsdQrUGNri0AYeM/Lq34Dbll8t8emH0EPQ iat-mode=0
Bridge obfs4 51.15.6.168:60001 E106884C809EC0BCC00F1BC28F0E0D4495B5B0AC cert=mDFa9ZSzOB7V9zFmt5q0OZTB3i50Dm9IkLcAHZJo+Oasvf8AsZgo47lLVk+7vH1q3Hrkfw iat-mode=0


NewCircuitPeriod 900
KeepalivePeriod 900

CircuitsAvailableTimeout 1800
CircuitStreamTimeout 60

HashedControlPassword 16:0F176D25F839C73F60685112A2CB8CFE97161C035B672335C8658CD5A0
ControlPort 9051
CookieAuthentication 1

```

## obfs4proxy
国内编译的时候，因为golang网站不能正常访问，所以会出现编译mod不全的情况，且无法下载.<br>
最新编译的版本仅用于buntu.<br>
obfs4proxy is only used for ubuntu1804.
