# 10 vCenter操作

1.添加vCenter

点击集群界面的添加VCenter按钮，进入添加vCenter界面。如图10-1-1所示。

* 目前只允许用户添加一个vCenter

![png](../images/10-1-1.png "图10-1-1未添加vCenter集群界面")

###### 图10-1-1 未添加vCenter集群界面


![png](../images/10-1-2.png "图10-1-2集群结构图")

###### 图10-1-2 添加vCenter界面

2.删除vCenter

当用户添加成功一个vCenter后，集群界面中“添加vCenter”按钮变为“删除vCenter”按钮。如图10-1-3所示。**删除vCenter后会清除其上所有资源在Mevoco中的记录，并不会删除vCenter上的真实资源。**（VMware vSphere Client上登录依然可以看到完整的已部署的VMware环境）

* 注意：勾选任意集群，出现红色的集群删除按钮，该按钮只对KVM集群生效。

![png](../images/10-1-3.png "图10-1-3 已添加vCenter集群界面")

###### 图10-1-3 已添加vCenter集群界面

点击“删除vCenter”按钮，弹出确认提示框，点击确定会清除vCener。
![png](../images/10-1-4.png "图10-1-4删除vCenter界面")

###### 图10-1-4 删除vCenter界面
