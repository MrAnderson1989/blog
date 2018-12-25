# 镜像版本问题

运行命令：

docker-machine create --driver virtualbox manager1

输出：

Unable to get the local Boot2Docker ISO version: Did not find prefix \"-v\" in version string"

Default Boot2Docker ISO is out-of-date, downloading the latest release...

github相关问题讨论：https://github.com/boot2docker/boot2docker/issues/1347

docker-machine 错误代码地址：https://github.com/docker/machine/blob/master/libmachine/mcnutils/b2d.go#L310

解决方案：使用 [HexEditor](https://hexed.it/) 修改对应版本号位置，加上 -v18.09.x（-v18.09.1）然后导出镜像复制到 /home/{user}/.docker/machine/cache 目录，再次运行create 命令问题解决。

