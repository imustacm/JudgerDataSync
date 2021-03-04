# JudgerDataSync
在拥有多个判题机服务的情况下，不同的判题机之间，需要快速同步判题用到的测试数据。

## 解决方案

使用[inotify](https://zh.wikipedia.org/zh-cn/Rsync) + [rsync](https://zh.wikipedia.org/wiki/Inotify) 进行多服务器下数据同步问题。

使用一台判题服务器作为主服务器端，其他判题服务器作为从服务器。修改主服务器上测试数据后，主服务器对从服务器进行数据同步。

## 主服务器需要执行以下脚本

```shell
./autoSync
```

## 从服务器需要执行以下脚本

```shell
./rsync_daemon.sh
```