# shadowsocks-python
shadowsocks-python

在 https://teddysun.com/342.html 的脚本上修改的,

增加判断系统是使用 firewall 还是 iptable , 以及对应操作.
  如果是 firewall , 创建 /usr/lib/firewalld/services/shadowsocks.xml , 做为服务类型添加到 firewall 里面.
增加判断文件,不重复下载, 虽然不大 XD.

自己玩的... 

# install

安装之前确保 firewall/iptable 是在启动的状态.

wget --no-check-certificate https://raw.githubusercontent.com/otoil/shadowsocks-python/master/shadowsocks-check-firewall.sh
chmod +x shadowsocks-check-firewall.sh
./shadowsocks-check-firewall.sh 2>&1 | tee shadowsocks.log

配置文件路径：/etc/shadowsocks.json

使用命令：
启动：/etc/init.d/shadowsocks start
停止：/etc/init.d/shadowsocks stop
重启：/etc/init.d/shadowsocks restart
状态：/etc/init.d/shadowsocks status

