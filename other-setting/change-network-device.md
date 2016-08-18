# 19.9 CentOS7网卡设备编号变更

CentOS7系统默认的网卡设备名称默认不是ethx格式，如果系统在安装时，点击tab键，在grub中加入“net.ifnames=0”参数，再进行安装，则设备默认会是ethx格式。

如果系统已经安装完毕，可以通过以下步骤进行设置将其改为ethx格式（本例将em01设备改为eth0）：

1.在/etc/default/grub的GRUB_CMDLINE_LINUX变量追加“net.ifnames=0”参数

2.在终端执行grub2-mkconfig -o /boot/grub2/grub.cfg 更新grub配置生效

3.修改/etc/sysconfig/network-scripts/ifcfg-em01中“DEVICE=em01”修改为“DEVICE=eth0”, 并将此文件重命名为ifcfg-eth0

4.修改/etc/udev/rules.d/70-persistent-net.rules里面对设备的定义，如果此文件不存在，则按照以下格式创建，例如将原来em01的网卡指定为如下信息：

` SUBSYSTEM=="net", ACTION=="add", DRIVERS=="?*", ATTR{address}=="00:1e:67:e7:8c:78", ATTR{dev_id}=="0x0", ATTR{type}=="1", KERNEL=="eth*", NAME="eth0"
`

5.如果系统有多块网卡，则参考第3-4步重复修改，系统重启后修改网卡设备名称生效。

