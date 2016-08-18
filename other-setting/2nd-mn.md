# 19.1 安装第二个管理节点

当管理大量物理机的时候，为了提高可用性，用户可以安装多个Mevoco管理节点。多个Mevoco管理节点之间关系平等，相互支撑。用户可以使用如下的方法安装：

`zstack-ctl install_management_node --host=ip_of_machine_to_install_node_2 --yum=alibase,aliepel`

当新节点成功安装后，请在新节点上配置新管理节点的IP地址：

```
zstack-ctl configure management.server.ip=ip_of_management_node2
zstack-ctl save_config
```

可以重复这一步来安装更多的管理节点。如果启动了多个管理节点，在批量创建云主机时，需要修改安装了mysql的管理节点的配置文件/etc/my.conf，将其中的最大连接数修改为适合的值，来增加可接受的最大并发数量。假如有三个管理节点，启动一百个云主机，最大并发数量至少需高于300，下例设置为500，可作为参考：

```
vim /etc/my.conf
max_connections = 500
```

如果用户购买了Mevoco使用授权，请联系销售厂商给每一个管理节点单独安装一个授权协议。

在多管理节点需要升级时，需将所有的管理节点的服务通过”zstack-ctl stop”全部停止，在第一台管理节点通过-u 参数升级，第二台管理节点通过以下方式升级：

```
zstack-ctl upgrade_management_node --host=ip_of_machine_to_upgrade_node_2 --war-file=/usr/local/zstack/zstack.war
```


升级完毕后，需启动两台管理节点的服务。其他管理节点可参考第二台管理节点的升级过程进行升级，升级过程中所有的管理节点的服务需停掉。

全部升级完毕后再次开启服务。

