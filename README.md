# webase-deploy-macos

## 修改系统检查脚本
```
vi webase-deploy/comm/check.py
    # get free memory(M)
    # Linux
    # memFree=doCmd("awk '($1 == \"MemFree:\"){print $2/1024}' /proc/meminfo 2>&1")
    # MacOS
    memFree=doCmd("top -l 1 | head -n 10 | grep PhysMem | awk '{print $6}' | cut -d'M' -f1")
```

## 修改构建脚本
```
vi webase-deploy/comm/build.py
        #Linux
        #doCmd('sed -i "s/nodeCounts/{}/g" nodeconf'.format(node_nums))
        #MacOS
        doCmd('sed -i "" "s|nodeCounts|{}|g" nodeconf'.format(node_nums))
```
