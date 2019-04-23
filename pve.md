调整lvs大小

```bash
#查free LogicalExtentsNumber数字，先查有多少free LogicalExtentsNumber可用
vgdisplay pve |grep Free

#调整大小
lvresize -l +<LogicalExtentsNumber> <VG>/<LVThin_pool>
```



