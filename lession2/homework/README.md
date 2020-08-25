###环境:
```bash
ID                 Role          Host         Ports        OS/Arch       Status  Data Dir                      Deploy Dir
--                 ----          ----         -----        -------       ------  --------                      ----------
172.17.0.26:9093   alertmanager  172.17.0.26  9093/9094    linux/x86_64  Up      /tidb-data/alertmanager-9093  /tidb-deploy/alertmanager-9093
172.17.0.25:3000   grafana       172.17.0.25  3000         linux/x86_64  Up      -                             /tidb-deploy/grafana-3000
172.17.0.24:2377   pd            172.17.0.24  2377/2376    linux/x86_64  Up|UI   /tidb-data/pd-2377            /tidb-deploy/pd-2377
172.17.0.25:2377   pd            172.17.0.25  2377/2376    linux/x86_64  Up      /tidb-data/pd-2377            /tidb-deploy/pd-2377
172.17.0.26:2377   pd            172.17.0.26  2377/2376    linux/x86_64  Up|L    /tidb-data/pd-2377            /tidb-deploy/pd-2377
172.17.0.24:9090   prometheus    172.17.0.24  9090         linux/x86_64  Up      /tidb-data/prometheus-9090    /tidb-deploy/prometheus-9090
172.17.0.24:4000   tidb          172.17.0.24  4000/10080   linux/x86_64  Up      -                             /tidb-deploy/tidb-4000
172.17.0.25:4000   tidb          172.17.0.25  4000/10080   linux/x86_64  Up      -                             /tidb-deploy/tidb-4000
172.17.0.26:4000   tidb          172.17.0.26  4000/10080   linux/x86_64  Up      -                             /tidb-deploy/tidb-4000
172.17.0.24:20160  tikv          172.17.0.24  20160/20180  linux/x86_64  Up      /tidb-data/tikv-20160         /tidb-deploy/tikv-20160
172.17.0.25:20160  tikv          172.17.0.25  20160/20180  linux/x86_64  Up      /tidb-data/tikv-20160         /tidb-deploy/tikv-20160
172.17.0.26:20160  tikv          172.17.0.26  20160/20180  linux/x86_64  Up      /tidb-data/tikv-20160         /tidb-deploy/tikv-20160

磁盘是机械磁盘，IO延迟比较高
3台docker，cpu限制2核，内存4G
```
1. 重新跑了sysbench，规格比笔记本虚机好一些
2. 磁盘是机械磁盘，IO延迟比较高
3. 执行sysbench过程中，进入其中一个docker执行top查看cpu基本上能达到200%
4. 瓶颈应该是磁盘，延迟太高