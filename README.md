# 此OpenShift基于开源版本Minishift在redhat linux上搭建.

### 关于Minishift

1.官方API地址：https://docs.okd.io/latest/minishift/index.html


2.Linux开机自动运行Minishift脚本。'.sh'
```
# !/bin/bash
export MINISHIFT_GITHUB_API_TOKEN="7769e43402861e7d7490692451591aed68ce9300"
echo "start run!"
systemctl start libvirtd
if [ $? -eq 0 ];then
echo "libvirtd run successful!"
else
echo "libvirtd run faild."
fi
cd /opt/minishift
if [ $? -eq 0 ];then
echo "path to /opt/minishift successful!"
else
echo "path to /opt/minishift faild.."
fi
/opt/minishift/minishift start
if [ $? -eq 0 ];then
echo "minishift start successful."
else
echo "minishift start faild."
fi
sleep 1m
eval $(/opt/minishift/minishift docker-env)                                    22,1         顶端

```
