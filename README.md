竹林再遇北极熊制作于2019年8月10日，今晚真的很像士兵许三多一样难过，在连长(老大)都走了以后，1个人守着1个人的连队(小组)，想起钢七连"不抛弃，不放弃"的精神，希望这种事不会再经历，真难熬

    v1.0 建立
    v1.1 优化
    v20210425 优化，优化内容详见Releases
    原则：不运行，不自启直到是威胁其影响也是微乎其微的，
    作用：好记性不如烂笔头，自动化收集操作系统中的现象、持久化、痕迹，并将无用信息进行过滤，方便检查,即只做信息收集不做过多判断；例如快速获取某个程序的启动方式
    翻译：百度翻译
    指南：使用root权限在当前目录下运行start.sh，根据提示输入服务器ip，检查记录存档于当前文件夹的【$HostIp_$SystemDate-results/*】目录下

第三方工具，可自行至源站下载、编译、替换

1 busybox  防止系统命令被替换以及脚本兼容性

    下载
        https://busybox.net/downloads/busybox-1.32.1.tar.bz2
    编译
        make defconfig
        make CROSS_COMPILE=""

2 chkrootkit  rootkit检查工具

    下载
        ftp://ftp.pangeia.com.br/pub/seg/pac/chkrootkit.tar.gz
    编译
        make sense
        yum -y install glibc-static 如果报"/usr/bin/ld：找不到 -lc"错误时

3 hm  webshell查杀工具

    下载
    http://dl.shellpub.com/hm/latest/hm-linux-amd64.tgz?version=1.8.2

异常文件删除方法

    加锁
        chattr -i test.sh && ./rm -rf test.sh
    隐藏空格，转义符，连接符，显示名称乱码
        执行命令ls -li获取该文件的inode，find . -type f -inum inodeNumber -delete

检查内容

    0 创建检查目录和输出文档
    1 现象检查
        1.1 已监听端口
        1.2 已建立连接
        1.3 系统进程
    2 持久化检查
        2.1 任务计划
        2.2 环境变量
        2.3 系统服务
        2.4 账户权限
        2.5 rootkit
    3 痕迹检查
        3.1 登陆日志
        3.2 文件落地
        3.3 历史命令
        3.4 防火墙
        3.5 杀毒软件(手动检查)
