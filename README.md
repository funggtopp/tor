<font color=red> 自用的，主要是用来上上谷歌邮箱，在油管上骂骂汉奸之类</font> <br>
Tor will creat LISTEN port at 127.0.0.1:9050.<br>
You can modify it in torrc
## windows tor

tor.zip is for windwos

## linux tor
you should use <code>tor -f torrc</code> to run your tor.

## torrc
torrc is a very important file,especially if you are in ...
Your torrc maybe like this:

```
SocksPort 172.22.172.22:9050
#HTTPSProxy 127.0.0.1:8787
#Socks5Proxy 127.0.0.1:1080
UseBridges 1
AvoidDiskWrites 1
#StrictNodes 1
#ExcludeExitNodes {cn},{hk},{mo},{sg},{th},{pk},{by},{ru},{ir},{vn},{ph},{my},{cu}  
#ExcludeNodes {cn},{hk},{mo},{sg},{th},{pk},{by},{ru},{ir},{vn},{ph},{my},{cu}  
ClientTransportPlugin obfs4 exec ./obfs4proxy managed

Bridge obfs4 185.35.77.166:443 C21CA3ECCAD6A5DAA4992F49D829385268ABD5F5 cert=qagdYHpQz6W5Rb2U3BAdaK4QQbnLBZKH3KYpGM6ZNBS3AiuRBcH9P1HIo9VgGgCXRJQaCA iat-mode=0
Bridge obfs4 212.21.66.66:20621 986E06A61EC62DC0DD58E0A1BB6EE54463EF408A cert=ifbMX0EZ6eqTfCuyiiR0LDEZVX2UVGHEFvqbu5qb6wCZELi5WYhEEWIIBek5MSvyTQx3CA iat-mode=0
Bridge obfs4 185.163.46.63:443 60728A289529B2A0819BC7DC7A73A780567B73C8 cert=xNfHXSkbUcJDlLOsZ3wM6swwI1LIvRgySKJdY4liYbOVCdBVKPErgVSav2DPfGzN1ZpxJQ iat-mode=0
Bridge obfs4 195.201.14.15:37361 3BECEABD174AE41C5CCC17254A40DD24EC5372CD cert=vlSA6qJIck/UH66T/2yoMtE44lbIEJ9fLCpwUl5ffGWBT6gUYU62sQLz9EIv5DrbROm1Og iat-mode=0
Bridge obfs4 80.209.236.183:443 0875F92379ACA7CC3ADB3FC176338B28EF307161 cert=gcWOwepy4SUWha+KBYDOYAv6Kqyf2L52ehHG/Nq7vryLcPEqU5B0776CzI+BuyUzY7JqFg iat-mode=0
#for testing 
NewCircuitPeriod 900
```

## obfs4proxy
国内编译的时候，因为golang网站不能正常访问，所以会出现编译mod不全的情况，且无法下载.<br>
最新编译的版本仅用于buntu.<br>
obfs4proxy is only used for ubuntu1804.
