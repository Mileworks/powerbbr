简介

BBR相信大家都不陌生，是谷歌开发的一个存在于Linux内核中的拥塞算法。为了优化国内与服务器之间的网络质量，loc的大佬专门魔改改进了下这个BBR，成为了新的BBR魔改版。我也就乘机水一篇文章好了~在Debian 8 和Ubuntu16 + 系统上一键部署魔改版BBR，自动换内核成 4.10.15 ，自动安装Headers。用户只需要将系统安装成 Debian 8 或者 Ubuntu 16 即可，剩下的交给脚本来吧。
Github地址:https://github.com/FunctionClub/YankeeBBR
bbr1.png
参考资料

魔改BBR原帖：http://www.hostloc.com/thread-372277-1-2.html
萌新教程: http://www.hostloc.com/thread-372335-1-1.html
脚本技术： https://doub.io/wlzy-16/

部分商家的VPS可能会遇到换内核之后无法启动系统的情况，所以请运行脚本前一定要备份好重要数据！！
安装使用

wget -N --no-check-certificate https://raw.githubusercontent.com/FunctionClub/YankeeBBR/master/bbr.sh && bash bbr.sh install

安装过程中如果出现这张图片，请选择NO 来删除其他内核：

bbr2.png

然后根据提示重启系统。
重启完成后，运行

bash bbr.sh start

即可启动魔改版BBR。
查看魔改BBR状态

sysctl net.ipv4.tcp_available_congestion_control

如果看到有 tsunami 就表示开启成功！

bbr3.png
