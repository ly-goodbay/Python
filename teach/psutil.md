# psutil 模块

```shell
#psutil.cpu_times(percpu=False)  #查看CPU所有信息
scputimes(user=306.98, nice=2.01, system=337.34, idle=410414.39, iowait=78.37, irq=0.0, softirq=17.42, steal=0.0, guest=0.0, guest_nice=0.0)

#user:用户进程花费的时间
#nice：用户模式执行Niced优先级进程花费的时间
#system：内核模式进程花费的时间
#idle：闲置时间
#iowait:等待I/O完成的时间
#irq：处理硬件中断的时间
#softirq：处理软件中断的时间
#steal：虚拟化环境中运行的其他操作系统花费的时间
#guest：在linux内核的控制下为客户端操作系统运行虚拟CPU所花费的时间
#guest_nice：虚拟机运行niced所花费的时间
```

```shell
#psutil.cpu_count(logical=True) #显示cpu逻辑个数
#psutil.cpu_count(logical=False)  #显示CPU物理个数
```

```python
#psutil.cpu_stats()   #CPU统计信息
scpustats(ctx_switches=9838934, interrupts=10572621, soft_interrupts=5582125, syscalls=0)

#ctx_switches：启动后的上下问切换次数
#interrupts：自启动以来的中断次数
#soft_interrupts：启动后的软件中断数量
#syscalls：启动以来的系统调用次数,linux为0
```

```python
#mem = psutil.virtual_memory()  #获取内存完整信息
svmem(total=2078892032, available=1508818944, percent=27.4, used=367063040, free=135192576, active=874614784, inactive=694231040, buffers=122880, cached=1576513536, shared=10444800, slab=255148032)

#total:总物理内存
#available:可用的内存
#used:使用的内存
#free：完全没有使用的内存
#active：当前正在使用的内存
#inactive：标记为未使用的内存
#buffers：缓存文件系统元数据使用的内存
#cached:缓存各种文件的内存
#shared:可以被多个进程同时访问的内存
#slab:内核数据结构缓存的内存

#psutil.swap_memory()  #获取swap内存信息
sswap(total=2148528128, used=270336, free=2148257792, percent=0.0, sin=0, sout=12288)

#total：以字节为单位的总交换内存
#used：以字节为单位使用交换内存
#free：以字节为单位的可用交换内存
#percent：使用百分比
#sin：系统从磁盘交换的字节数
#sout：系统从磁盘换出的字节数
```

```python
#psutil.disk_partitions(all=False) #获取磁盘完整信息
[sdiskpart(device='/dev/sda3', mountpoint='/', fstype='xfs', opts='rw,seclabel,relatime,attr2,inode64,noquota'),
 sdiskpart(device='/dev/sda5', mountpoint='/home', fstype='xfs', opts='rw,seclabel,relatime,attr2,inode64,noquota'),
 sdiskpart(device='/dev/sda1', mountpoint='/boot', fstype='xfs', opts='rw,seclabel,relatime,attr2,inode64,noquota')]

# device  设备名称
# mountpoint 挂载目录
# fstype 文件系统类型
# opts 挂载方式
```

```shell
#psutil.disk_usage('/')  #获取分区使用情况
sdiskusage(total=53660876800, used=3662462976, free=49998413824, percent=6.8)

#total：总的大小（字节）
#used：已使用的大小（字节）
#free：空闲的大小（字节）
#percent：使用百分比
```

```python
#psutil.disk_io_counters(perdisk=False,nowrap=True) #将系统范围的磁盘I/0统计作为命名元组返回 如果perdisk为True 区分单个分区                   
sdiskio(read_count=20173, write_count=196206, read_bytes=777824768, write_bytes=2732865536, read_time=207425, write_time=363200, read_merged_count=57, write_merged_count=6063, busy_time=277196)

#read_count：读取次数
#write_count：写入次数
#read_bytes：读取的字节数
#write_bytes：写入的字节数
#read_time：从磁盘读取的时间（以毫秒为单位）
#write_time：写入磁盘的时间（毫秒为单位）
#busy_time：花费在实际I/O上的时间
#read_merged_count：合并读取的数量
#write_merged_count：合并写入次数
```

```python
In [6]: import psutil,time                                                     
In [7]: psutil.boot_time()  #系统启动时间戳                                     
Out[7]: 1567342872.0
In [9]: time.strftime('%Y-%m-%d %H:%M:%S',time.localtime(psutil.boot_time()))            
Out[9]: '2019-09-01 21:01:12'
```

```python
In [10]: psutil.users()  # 查看当前连接的用户                                                         
Out[10]: 
[suser(name='root', terminal='tty1', host='', started=1567070080.0, pid=6547),
 suser(name='root', terminal='pts/0', host='192.168.252.1', started=1567433088.0, pid=82270),
 suser(name='root', terminal='pts/1', host='192.168.252.1', started=1567433088.0, pid=82287),
 suser(name='root', terminal='pts/2', host='192.168.252.1', started=1567436416.0, pid=11672),
 suser(name='root', terminal='pts/3', host='192.168.252.1', started=1567436416.0, pid=11673),
 suser(name='root', terminal='pts/4', host='192.168.252.1', started=1567436416.0, pid=16554),
 suser(name='root', terminal='pts/5', host='192.168.252.1', started=1567436416.0, pid=16559)]

```

