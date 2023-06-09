# Usage Guide<a name="EN-US_TOPIC_0000001196305050"></a>

You can run the  **gs\_dbmind**  command to start an exporter. The following describes how to set up a complete Prometheus monitoring platform.

1.  Run the following command to start Prometheus and all exporters:

    ```
    gs_dbmind component deployment --run
    ```

    For details about how to start Prometheus and each exporter, see the following steps. If you use only the automatic deployment tool to deploy Prometheus, go to [6](#li0810649203213).

2.  Run the following command to deploy the Prometheus main process:

    ```
    prometheus --config.file=prometheus.yml
    ```

3.  Deploy openGauss-exporter. Run the following command to start openGauss-exporter, use the default listening port number 9187, set the listening IP address to 192.168.1.100, and disable HTTPS:

    ```
    gs_dbmind component opengauss_exporter --url postgresql://user:password@ip:port/dbname --web.listen-address 192.168.1.100 --disable-https
    ```

4.  Deploy reprocessing-exporter. Run the following command to start reprocessing-exporter, use the default listening port number 8181, set the listening IP address to 192.168.1.101, the IP address and port number of the Prometheus server to 192.168.1.100 and 9090, and disable HTTPS:

    ```
    gs_dbmind component reprocessing_exporter 192.168.1.100 9090 --web.listen-address 192.168.1.101 --ssl-keyfile server.key --ssl-certfile server.crt 
    ```

5.  Deploy cmd-exporter: Start cmd-exporter, use the default parameters, and specify the certificate information.

    ```
    gs_dbmind component cmd_exporter --ssl-keyfile server.key --ssl-certfile server.crt 
    ```

6.  <a name="li0810649203213"></a>Deploy node-exporter. Generally, node-exporter needs to be deployed on the Prometheus monitoring platform to monitor the Linux OS. Some AI functions mentioned in the following sections also depend on node-exporter to collect Linux system metrics. Therefore, node-exporter also needs to be deployed by users. For details, visit https://prometheus.io/docs/guides/node-exporter/\#installing-and-running-the-node-exporter.

  You can run the node-exporter process. The default port number is 9100. The command for starting the process is as follows:

    ```
    node_exporter 
    ```

7.  You can run commands to monitor the running status of Prometheus and all exporters.

    ```
    gs_dbmind component deployment --check
    ```


>![](public_sys-resources/icon-caution.gif) **CAUTION:** 
>-   To connect to a database from openGauss-exporter, you must have the  **monitor admin**  permission or higher. Otherwise, some metrics cannot be collected.
>-   openGauss-exporter samples slow SQL information from the  **dbe\_perf.statement\_history**  view. The slow SQL records in  **dbe\_perf.statement\_history**  are related to  **log\_min\_duration\_statement**  and  **track\_stmnt\_stat\_level**.  **log\_min\_duration\_statement**  indicates the slow SQL threshold, in milliseconds. You can set it to a specific value as required.  **track\_stmnt\_stat\_level**  indicates the SQL record level. The default value is  **'OFF,L0'**, indicating that only slow SQL statements are recorded. The level is L0. Exercise caution when modifying this parameter.
>-   openGauss-exporter collects database information, including data in some system catalogs and views \(for details, see the opengauss\_exporter configuration file\), node-exporter collects system metrics, mainly related to system disks and CPUs, and reprocessing\_exporter performs secondary processing based on some metrics in prometheus-server \(for details, see the reprocessing\_exporter configuration file\). Then, the processed data is provided to users.
>-   Prometheus-server has a timeout mechanism when pulling exporter data. The timeout interval is controlled by  **scrape\_timeout**  \(10s by default\). Therefore, when the exporter collects a large amount of data, you can increase the value of  **scrape\_timeout**  as required to prevent timeout errors. Note that the value of **scrape\_interval** (collection interval, 15s by default) cannot be smaller than that of **scrape\_timeout**.Otherwise, an exception occurs.
>-   Ensure that the time zone of the database is consistent with that of the system; otherwise, the time of time-related metrics may be inconsistent with the system time.
>-   When HTTPS is used for communication, the tool checks the permission on the certificate and key file and the validity period of the certificate. If the file permission is greater than 600, an alarm is generated. If the certificate will expire within 90 days, an alarm is generated.
>-   When metrics are repeatedly collected, an exception occurs on openGauss-exporter, and the exception information is recorded in logs.
>-   When setting the  **--config**,  **--disable-settings-metrics**  and  **--disable-statement-history-metrics**  parameters of openGauss-exporter, please note that:
>    1.  If you do not specify any of them, the tool collects metrics in the three configuration files in the  **yamls**  directory at the same time.
>    2.  If you explicitly specify  **--config**, the tool does not collect metrics in the  **default.yml**  file in the  **yamls**  directory, but collects metrics in the specified configuration file. In addition, metrics in the  **pg\_settings.yml**  and  **statements.yml**  files can be properly collected. In this case, ensure that the metrics in the specified configuration file and those in  **pg\_settings.yml**  and  **statements.yml**  are not repeatedly collected.
>    3.  If you explicitly specify  **--disable-settings-metrics**, the tool does not collect metrics in  **pg\_settings.yml**  in the  **yamls**  directory. If you explicitly specify  **--disable-statement-history-metrics**, the tool does not collect metrics in  **statements.yml**  \(related to slow SQL\) in the  **yamls**  directory.
>-   Generally, after the exporter is started, it does not terminate the process and exit (for example, the address of the connected database is unavailable, or the connected database user is deleted or disabled). Instead, it records the error information in the log and tries again in the background.
