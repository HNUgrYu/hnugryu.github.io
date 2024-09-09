## 怎么连接vpn后访问一些校园网站
1. 找到要连接校园网的网站ip地址
`nslookup gym.hnu.edu.cn`
2. 在clash verge中加入这个IP地址
- 在订阅情况下：
点击订阅找到修改文件，在rule中加入
`DOMAIN-SUFFIX,gym.hnu.edu.cn,DIRECT`
