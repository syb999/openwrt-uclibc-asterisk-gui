# openwrt-uclibc-asterisk-gui

按照下面的模板修改/etc/asterisk/http.conf:
[general]
enable=yes
bindaddr=0.0.0.0
bindport=8088
enablestatic=yes
sessionlimit=100
session_inactivity=30000

按照下面的模板修改/etc/asterisk/manager.conf:
enabled = yes
webenabled = yes
port = 5038
bindaddr = 0.0.0.0

[admin]
secret = admin
read = system,call,log,verbose,agent,user,config,dtmf,reporting,cdr,diaplan
write = system,call,agent,user,config,command,reporting,originate,message

登录ssh：
asterisk -rvvv
core restart now
asterisk -rvvv

访问web使用asterisk-gui:
http://lan-ip:8088/static/config/index.html

