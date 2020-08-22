# TNT
针对于默认端口的自动化爆破工具。
该项目改编自[t14m4t](https://github.com/MS-WEB-BN/t14m4t)
但是由于作者字典太多且复杂，难于管理，就顺手改了一下。


- hydra部分
修改hydra不显示详情（去除-v参数），不然太多了眼花缭乱的。
- 字典
去除了大部分的字典文件，合并username和password至UaP.txt里，并且扩充了一部分常用密码。另外保留了oracle和postgrep的原始字典文件用做对这两个服务的爆破。
- 修复了[t14m4t](https://github.com/MS-WEB-BN/t14m4t)原始项目中，作者写错的代码和一些奇奇怪怪的问题。

## Usage:
和原版没变动

```
# ./TNT <target> <number of threads>
```
#### Example


```
# ./TNT xx.xx.xx.xx 32
# ./TNT /targets/targetlist.txt 32
```
默认线程为16

## 场景
个人觉得该工具适合的应用场景如下：
1、单IP存在多个默认服务端口：
该情况下可以用此工具快速检索所有暴露的服务是否存在弱口令。
2、多IP列表的单/多个默认服务端口：
该情况下用来批量扫描也是不错。其他工具的批量扫描只适合针对IP列表的单个端口来做爆破。

##  注意：
该工具就只是个bash脚本，还需要配合hydra和nmap来使用，所以最好是直接装在kali里面，这样hydra的各种依赖库就不用自己再去装了。