# 非root用户加入docker用户组省去sudo

1.使用有sudo权限的帐号登录到服务器系统
```
sudo cat /etc/group | grep docker
```
2.将相应的用户添加到这个分组里面
```
sudo usermod -aG dockerroot loginuser
```
3.重启docker-daemon
```
systemctl restart docker
```
4.确认你可以直接运行docker命令，执行docker命令
```
docker  info
```
5.如果提示get ......dial unix /var/run/docker.sock权限不够，则修改/var/run/docker.sock权限
```
chmod a+rw /var/run/docker.sock
```
