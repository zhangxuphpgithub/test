准备阶段
1、cat /etc/redhat-release   5或者7 版本记录一下
2、ifconfig 查看网卡类型于块数 在网页监控中更改相应的模板(以前为host，更改为srv)
3、df -h 如果出现除/ /opt两个目录有其他大容量硬盘请记录，并在网页监控中重新添加相应模板 (/data  /opt/onling01两种，有其他模板的没有的硬盘可以添加)
4、确保custom.repo存在  rpmforge.repo改名为rpmforge.repo.bak
指令：1、cd /etc/yum.repos.d   2、mv rpmforge.repo rpmforge.repo.bak
5、ps aux|grep nrpe
nagios    1916  0.0  0.0  41312  1344 ?        Ss   Oct02   0:35 /usr/sbin/nrpe -c /etc/nagios/nrpe.cfg -d   

安装阶段
1、yum clean all
2、yum -y install monitor-agent

5、重启监控页面，如还报警参考以下步骤：
/etc/init.d/nrpe restart   /usr/sbin/nrep -c /etc/nagios/nrep.cfg -d
删除监控页面原有列表重新建立
6、检查nrpe的版本 
[root@wx-b11-30-124 ~]# rpm -qa nrpe
    nrpe-2.15-2.el6.x86_64


检查nrpe配置文件   cat /etc/nagios/nrpe.cfg
检查nrpe下的文件   ls /etc/nrpe.d/
重新安装           yum -y remove monitor-agent && yum -y install monitor-agent




nrpe路径不在usr/sbin/nrpe   如果在usr/local/目录下的话，
解决这个的方法  先杀死nrpe进程。
               1. rm -rf /etc/init.d/nrpe* 
               2. yum remove nrpe monitor-agent 
               3. yum install monitor-agent



出现提示：Error:Package:perl-IO-Compress-2.052....... 等很多缺失包裹报警 
解决办法：yum install perl-Compress-Raw-Zlib-2.052-1.el6.rfx.x86_64

如果/etc/yum.repos.d 下面没有安装包(custom.repo、rpmforge.repo)没有的话
解决办法:scp root@10.0.30.32:/etc/yum.repos.d/* ./etc/yum.repos.d/
         
          scp -r /etc/yum.repos.d/* root@10.10.111.21:/etc/yum.repos.d/ 在非本机操作

远程重启脚本

ipmitool -I lanplus -H 172.22.32.106 -U root -P tvmining chassis power status

10.0.153.222 MirrOrs@LJT@)!$   DNS 221.228.255.1

开机 	chassis power on 				
关机 	chassis power off 				
重启 	chassis power reset 				
状态 	chassis power status

重启下载程序脚本 initctl restart svscan


手动切换链路（LA机房）
ssh -p 29922 root@10.160.1.219

vim /etc/host

xxx.xxx.xxx.xxx wx.service.tvmining.com


/etc/init.d/dnsmasq restart

ssh -p 29922 root@10.160.1.220

vim /etc/host

xxx.xxx.xxx.xxx wx.service.tvmining.com


/etc/init.d/dnsmasq restart


for i in {21..51}; do scp -P 29922 /root/hosts.bak 10.160.1.$i:/etc/hosts; done
for i in {21..51}; do ssh -p 29922 10.160.1.$i 'initctl restart svscan'; done



IP 登陆：10.10.32.80
ps -ef|grep uwsgi
kill -9 ****
uwsgi --ini /opt/project/teamworkflow/uwsgi.ini
成功反馈：[uWSGI] getting INI configuration from /opt/project/teamworkflow/uwsgi.ini

KVM云主机操作地址：10.20.80.51/dashboard/          as1: yunwei, pw:yunwei    as2:  chengchao ,pw:chengchao
