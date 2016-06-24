###测试 & 生产环境一 docker配置

#测试环境：

//ssh登录测试环境一 <br>
jeepdeMac-mini:~ jeep$ ssh dev1<br>
Last login: Fri Jun 24 10:16:17 2016 from 113.110.181.105<br>

//查看linux发行版信息<br>
[centos@klook_dev1_app ~]$ lsb_release -a<br>
LSB Version:	:core-4.1-amd64:core-4.1-noarch:cxx-4.1-amd64:cxx-4.1-noarch:desktop-4.1-amd64:desktop-4.1-noarch:languages-4.1-amd64:languages-4.1-noarch:printing-4.1-amd64:printing-4.1-noarch<br>
Distributor ID:	CentOS<br>
Description:	CentOS Linux release 7.2.1511 (Core) <br>
Release:	7.2.1511<br>
Codename:	Core<br>

//查看mysql版本信息<br>
[centos@klook_dev1_app ~]$ mysql --version<br>
mysql  Ver 14.14 Distrib 5.6.28, for Linux (x86_64) using  EditLine wrapper

//查看go版本信息<br>
[centos@klook_dev1_app ~]$ go version<br>
go version go1.6 linux/amd64

//ssh登录测试环境二 dev2<br>
jeepdeMac-mini:klook_code jeep$ ssh dev2<br><br>
The authenticity of host 'sgdev2.klook.com (52.76.51.82)' can't be established.<br>
ECDSA key fingerprint is SHA256:tQPDthdEBEIkvDQTOjZzg70ErKPPER2BBx4eAp4iYhU.<br>
Are you sure you want to continue connecting (yes/no)? yes<br>
Warning: Permanently added 'sgdev2.klook.com,52.76.51.82' (ECDSA) to the list of known hosts.<br>
Last login: Thu Jun 23 22:04:12 2016 from 23.99.108.227<br>

//查看linux发行版信息<br>
[centos@klook_dev2_web ~]$ lsb_release -a<br>
LSB Version:	:core-4.1-amd64:core-4.1-noarch:cxx-4.1-amd64:cxx-4.1-noarch:desktop-4.1-amd64:desktop-4.1-noarch:languages-4.1-amd64:languages-4.1-noarch:printing-4.1-amd64:printing-4.1-noarch<br>
Distributor ID:	CentOS<br>
Description:	CentOS Linux release 7.2.1511 (Core) <br>
Release:	7.2.1511<br>
Codename:	Core<br>

//查看mysql版本信息<br>
[centos@klook_dev2_web ~]$ mysql --version<br>
mysql  Ver 14.14 Distrib 5.6.29, for Linux (x86_64) using  EditLine wrapper<br>

//查看go版本信息<br>
[centos@klook_dev2_web ~]$ go version<br>
go version go1.6.2 linux/amd64<br>

//ssh登录pro生产环境<br>
jeepdeMac-mini:~ jeep$ ssh pro<br>
Last login: Fri Jun 24 14:20:51 2016 from 113.110.181.105<br>
[centos@klook_pro1 ~]$ lsb_release -a<br>
-bash: lsb_release: 未找到命令<br>

[centos@klook_pro1 ~]$ cat /etc/*release<br>
CentOS Linux release 7.1.1503 (Core)<br>
NAME="CentOS Linux"<br>
VERSION="7 (Core)"<br>
ID="centos"<br>
ID_LIKE="rhel fedora"<br>
VERSION_ID="7"<br>
PRETTY_NAME="CentOS Linux 7 (Core)"<br>
ANSI_COLOR="0;31"<br>
CPE_NAME="cpe:/o:centos:centos:7"<br>
HOME_URL="https://www.centos.org/"<br>
BUG_REPORT_URL="https://bugs.centos.org/"<br>

CENTOS_MANTISBT_PROJECT="CentOS-7"<br>
CENTOS_MANTISBT_PROJECT_VERSION="7"<br>
REDHAT_SUPPORT_PRODUCT="centos"<br>
REDHAT_SUPPORT_PRODUCT_VERSION="7"<br>

CentOS Linux release 7.1.1503 (Core)<br>
CentOS Linux release 7.1.1503 (Core)<br>

[centos@klook_pro1 ~]$ go version<br>
go version go1.6 linux/amd64<br>
[centos@klook_pro1 ~]$ mysql --version<br>
mysql  Ver 14.14 Distrib 5.6.23, for Linux (x86_64) using  EditLine wrapper<br>
[centos@klook_pro1 ~]$ uname -a<br>
Linux ip-10-15-2-26.ap-southeast-1.compute.internal 3.10.0-229.1.2.el7.x86_64 #1 SMP Fri Mar 27 03:04:26 UTC 2015 x86_64 x86_64 x86_64 GNU/Linux
