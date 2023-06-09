安装<a name="ZH-CN_TOPIC_0000001120430818"></a>

## 前提条件<a name="section9955194683210"></a>

-   已完成用户组和普通用户的创建。
-   所有服务器操作系统和网络均正常运行。
-   普通用户必须有数据库安装包解压目录、安装目录、数据目录的读、写和执行权限，并且安装目录，数据目录必须为空，且安装目录和数据目录以及配置的日志目录不能存在交叉。
-   普通用户对下载的openGauss轻量版压缩包有执行权限。
-   安装前请检查指定的端口是否被占用，如果被占用请更改端口或者停止当前使用端口进程。
-   环境变量：新安装时请确保GAUSSHOME，GAUSSDATA，GAUSSLOG，GAUSSENV不存在，如果是执行配置启动等后续操作，确保这些环境变量对应的配置正确。

>![](public_sys-resources/icon-caution.gif) **注意：** 
>如果安装前没有执行关闭HISTORY记录禁用history命令，为防止历史记录敏感信息泄露，安装完成后请手动清理history中的敏感信息。
>若安装前已执行操作关闭HISTORY记录，请忽略该说明。

## 操作步骤<a name="section98663181331"></a>

1.  使用普通用户登录到openGauss轻量版包安装的主机，解压轻量版安装包到安装目录。

    ```
    tar -zxf openGauss-Lite-3.0.0-openEuler-aarch64.tar.gz -C ~/openGauss
    ```

2.  假定解压包的路径为/opt/software/openGauss，进入解压后目录。

    ```
    cd ~/openGauss
    ```

3. 执行install.sh脚本安装openGauss轻量版安装包。

   ```
   单机：echo password | sh ./install.sh --mode single -D ~/openGauss/data -R ~/openGauss/install  --start
   主备：
       1、主节点：echo password | sh ./install.sh --mode primary -D ~/openGauss/data -R ~/openGauss/install  -C "replconninfo1='localhost=ip1 localport=port1 remotehost=ip2 remoteport=port2'" --start
       2、备节点：echo password | sh ./install.sh --mode standby -D ~/openGauss/data -R ~/openGauss/install  -C "replconninfo1='localhost=ip1 localport=port1 remotehost=ip2 remoteport=port2'" --start
   ```

   >![](public_sys-resources/icon-note.gif) **说明：** 
   >
   >
   >
   >-   -D|--data-path：数据库数据路径， 不可和安装目录交叉，必须为空。
   >-   -R|--app-path：数据库安装路径，不可和数据目录交叉。
   >-   -l|--log-path：日志保存路径。
   >-   -f|--guc-file：guc配置文件，批量进行guc参数设置，默认为安装脚本同级文件opengauss\_lite.conf，可指定。
   >-   -m|--mode：节点类型，默认single，支持primary（主节点），standby（备节点），single（单机）。
   >-   -n|--nodename：实例名称，主节点默认master，备节点默认slave，单机默认single。
   >-   -P|--gsinit-parameter：初始化参数，具体详见文档《工具与命令参考》中的“系统内部使用的工具 \> gs\_initdb”章节，出于安全考虑，不建议使用该接口传递密码。建议使用echo和pipe方式来传递密码，如果主备密码设置的不一致，最终会使用主节点设置的密码，同时密码长度为8-32位。
   >-   -C|--dn\_guc：数据库配置参数，具体详见文档《工具与命令参考》中的“服务端工具 \> gs\_guc”章节。
   >-   --env-sep-file：分离环境变量文件，会将使用过程中需要的环境变量写到该文件中，默认为用户的bashrc文件，注意不要传递目录。
   >-   --start：安装完成是否启动集群，默认不启动。
   >-   --ulimit：是否进行最大文件数配置（配置数为1000000），默认不设置。
   >-   --cert-path：ssl证书路径，传递了该参数，ssl会被设置为on，同时会把该路径下证书拷贝到数据目录。
   >-   --ssl-client-ip：客户端ip，只有在--cert-path参数启用的时候生效，会把客户端ip添加到白名单里面。
   >-   -h|--help：打印使用说明。
   >
   >
   >
   >![](public_sys-resources/icon-caution.gif) **注意：** 
   >
   >
   >
   >- 因为每一步都是可重入的，所以如果分离了环境变量，每一步执行脚本需要指定环境变量路径。
   >
   >- 主备节点保证IP类型一致，如果主节点使用IPV6，备节点也请使用IPV6。
   >
   >- 如果有多个备节点，需要在每一个节点上安装的时候传递所有节点的信息，注意区分本机和远端的信息。
   >
   >- 如果进行ulimit设置的时候，报错ulimit: open files: cannot modify limit: Operation not permitted，请使用root权限，在/etc/security/limits.conf中修改该用户可配文件数量的上限。
   >
   >- 如果安装异常终止，请检查安装目录和数据目录是否符合预期条件，必要情况下手动清理环境变量。
   >
   >-   安装主备环境的时候，如果replconninfo中采用的是sslmode=verify-ca，会出现备机连不上主机的现象，需要通过以下方式解决
   >   $\{GAUSSDATA\}代表dn数据目录
   >   示例：sh install.sh -R \~/app -m primary -D \~/data -l \~/log --start -C "replconninfo1='localhost=xxx.xx.xx.x localport=xxxx remotehost=xxx.xx.xx.x remoteport=xxxx sslmode=verify-ca'"。
   >   
   >   操作步骤
   >   
   >   -   准备证书、私钥。有关生成证书操作，请参考《数据库管理指南》中的“管理数据库安全 \> SSL证书管理 \> 证书生成”章节。
   >       服务端各个配置文件名称约定：
   >       -   证书名称约定：server.crt。
   >       -   私钥名称约定：server.key。
   >       -   私钥密码加密文件约定：server.key.cipher、server.key.rand。
   >       客户端各个配置文件名称约定：
   >       -   证书名称约定：client.crt。
   >       -   私钥名称约定：client.key。
   >       -   私钥密码加密文件约定：client.key.cipher、client.key.rand。
   >       -   根证书名称约定：cacert.pem。
   >       -   吊销证书列表文件名称约定：sslcrl-file.crl。
   >   -   拷贝证书到各个节点的数据目录。
   >       1.  将服务端各个配置文件server.crt、server.key、server.key.cipher、server.key.rand拷贝到对应目录下。
   >       2.  将客户端各个配置文件client.crt、client.key、client.key.cipher、client.key.rand、cacert.pem（如果需要配置吊销证书列表，则列表中包含sslcrl-file.crl）拷贝到到对应目录下。
   >   -   加密用户密码 （可选，如果证书已经生成了私钥可跳过）
   >       -   主节点： gs\_guc encrypt -M server -K 数据库密码 -D $\{GAUSSDATA\}/
   >       -   备节点： gs\_guc encrypt -M client -K 数据库密码 -D $\{GAUSSDATA\}/
   >       其中$\{GAUSSDATA\}为数据目录
   >   -   配置ssl
   >       ```
   >       gs_guc set -D ${GAUSSDATA} -c "ssl=on" 
   >       gs_guc set -D ${GAUSSDATA} -c "ssl_ciphers = 'ALL'" 
   >       gs_guc set -D ${GAUSSDATA} -c "ssl_cert_file = 'server.crt'" 
   >       gs_guc set -D ${GAUSSDATA} -c "ssl_key_file = 'server.key'" 
   >       gs_guc set -D ${GAUSSDATA} -c "ssl_ca_file = 'cacert.pem'" 
   >       ```
   >   -   备节点导出如下环境变量（文件权限不能大于600）
   >       ```
   >       export PGSSLCERT="${GAUSSDATA}/client.crt"
   >       export PGSSLKEY="${GAUSSDATA}/client.key"
   >       export PGSSLROOTCERT="${GAUSSDATA}/cacert.pem"
   >       ```
   >   -   依次重启主备openGauss。
   >       ```
   >       gs_ctl restart -D ${GAUSSDATA} 
   >       ```



4.  安装执行完成后，使用ps和gs\_ctl查看进程是否正常。

    ```
    ps ux | grep gaussdb
    gs_ctl query -D /opt/data
    ```

    执行ps命令，显示类似如下信息：

    ```
    omm      24209 11.9  1.0 1852000 355816 pts/0  Sl   01:54   0:33 /opt/install/bin/gaussdb -D /opt/data
    omm      20377  0.0  0.0 119880  1216 pts/0    S+   15:37   0:00 grep --color=auto gaussdb
    ```

    执行gs\_ctl命令，显示类似如下信息：

    ```
    gs_ctl query ,datadir is /opt/data
    HA state:
        local_role                     : Normal
        static_connections             : 0
        db_state                       : Normal
        detail_information             : Normal
    
    Senders info:
        No information
        
     Receiver info:
    No information 
    ```


