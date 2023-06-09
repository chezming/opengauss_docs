# gs\_dumpall<a name="EN-US_TOPIC_0294749044"></a>

## Background<a name="en-us_topic_0059778372_section31221112348"></a>

gs\_dumpall, provided by openGauss, is used to export all database information, including the data of the default  **postgres**  database, data of user-specified databases, and global objects of all databases.

When gs\_dumpall is used to export data, other users can still access \(read or write\) databases.

gs\_dumpall can export complete, consistent data. For example, if gs\_dumpall is started to export entire database at T1, data of the databases at that time point will be exported, and modifications on the databases after that time point will not be exported.

The generated columns are not dumped during gs\_dumpall is used.

gs\_dumpall exports all databases in two parts:

-   gs\_dumpall exports all global objects, including information about database users and groups, tablespaces, and attributes \(for example, global access permissions\).
-   gs\_dumpall invokes gs\_dump to export SQL scripts from each database, which contain all the SQL statements required to restore databases.

The exported files are both plain-text SQL scripts. Use  [gsql](gsql.md)  to execute them to restore databases.

## Precautions<a name="en-us_topic_0059778372_s67532b3f6d2a42e183672fae6c4ba753"></a>

-   Do not modify any exported file. Otherwise, restoration may fail.
-   To ensure the data consistency and integrity, gs\_dumpall sets a share lock for a table to be dumped. If a share lock has been set for the table in other transactions, gs\_dumpall locks the table after it is released. If the table cannot be locked within the specified time, the dump fails. You can customize the timeout duration to wait for lock release by specifying the  **--lock-wait-timeout**  parameter.
-   During an export, gs\_dumpall reads all tables in a database. Therefore, you need to connect to the database as a database administrator to export a complete file. When you use gsql to execute SQL scripts, administrator permissions are also required to add users and user groups, and create databases.
-   If the database contains time series tables, gs\_dumpall cannot be used to export data.

## Syntax<a name="en-us_topic_0059778372_s991ca5afb6574130a742db3732d6f577"></a>

```
gs_dumpall [OPTION]...
```

## Parameter Description<a name="en-us_topic_0059778372_s8a1ffa824f1b4371a430896ee8fd2020"></a>

Common parameters:

-   -f, --filename=FILENAME

    Sends the output to the specified file. If this option is omitted, the standard output is used.

-   -v, --verbose

    Specifies the verbose mode. This will cause gs\_dumpall to output detailed object comments and start/stop times to the dump file, and progress messages to standard errors.

-   -V, --version

    Prints the gs\_dumpall version and exits.

-   --lock-wait-timeout=TIMEOUT

    Do not keep waiting to obtain shared table locks at the beginning of the dump. Consider it as failed if you are unable to lock a table within the specified time. The timeout duration can be specified in any of the formats accepted by SET statement\_timeout.

-   -?, --help

    Displays help about the command line parameters for gs\_dumpall and exits.


Dump parameters:

-   -a, --data-only

    Dumps only the data, not the schema \(data definition\).

-   -c, --clean

    Runs SQL statements to delete databases before rebuilding them. Statements for dumping roles and tablespaces are added.

-   -g, --globals-only

    Dumps only global objects \(roles and tablespaces\) but no databases.

-   -o, --oids

    Dumps OIDs as parts of the data in each table. Use this option if your application references the OID columns in some way \(for example, in a foreign key constraint\). If the preceding situation does not occur, do not use this parameter.

-   -O, --no-owner

    Do not output commands to set ownership of objects to match the original database. By default, gs\_dumpall issues the ALTER OWNER or SET SESSION AUTHORIZATION statement to set ownership of created schema elements. These statements will fail when the script is running unless it is started by a system administrator \(or the same user that owns all of the objects in the script\). To make a script that can be stored by any user and give the user ownership of all objects, specify -O.

-   -r, --roles-only

    Dumps only roles but not databases or tablespaces.

-   -s, --schema-only

    Dumps only the object definition \(schema\) but not data.

-   -S, --sysadmin=NAME

    Specifies the name of the system administrator during the dump.

-   -t, --tablespaces-only

    Dumps only tablespaces but not databases or roles.

-   -x, --no-privileges

    Prevents the dumping of access permissions \(grant/revoke commands\).

-   --column-inserts/--attribute-inserts

    Exports data by running the INSERT command with explicit column names \{INSERT INTO table \(column, ...\) VALUES ...\}. This will cause a slow restoration. However, since this option generates an independent command for each row, an error in reloading a row causes only the loss of the row rather than the entire table content.

-   --disable-dollar-quoting

    Disables the use of dollar sign \($\) for function bodies, and forces them to be quoted using the SQL standard string syntax.

-   --disable-triggers

    Reserved for function extension. The option is not recommended.

-   --inserts

    Dumps data when the INSERT statement \(rather than COPY\) is issued. This will cause a slow restoration. The restoration may fail if you rearrange the column order. The --column-inserts parameter is safer against column order changes, though even slower.

-   --no-security-labels

    Reserved for function extension. The option is not recommended.

-   --no-tablespaces

    Do not output statements to create tablespaces or select tablespaces for objects. All the objects will be created during the restoration process, no matter which tablespace is selected when using this option.

-   --no-unlogged-table-data

    Reserved for function extension. The option is not recommended.

-   --include-alter-table

    Exports information about deleted columns in the table.

-   --quote-all-identifiers

    Forcibly quotes all identifiers. This parameter is useful when you dump a database for migration to a later version, in which additional keywords may be introduced.

-   --dont-overwrite-file

    Do not overwrite the current file.

-   --use-set-session-authorization

    Specifies that the standard SQL SET SESSION AUTHORIZATION command rather than ALTER OWNER is returned to ensure the object ownership. This makes dumping more standard. However, if a dump file contains objects that have historical problems, restoration may fail. A dump using SET SESSION AUTHORIZATION requires the system administrator permissions, whereas ALTER OWNER requires lower permissions.

-   --with-encryption=AES128

    Specifies that dumping data needs to be encrypted using AES128.

-   --with-key=KEY

    The AES128 key rules are as follows:

    -   Consists of 8 to 16 characters.
    -   Contains at least three of the following character types: uppercase characters, lowercase characters, digits, and special characters \(limited to \~!@\#$ %^&\*\(\)-\_=+\\|\[\{\}\];:,<.\>/?\).

-   --include-extensions

    Backs up all CREATE EXTENSION statements if the include-extensions parameter is set.

-   --include-templatedb

    Includes template databases during the dump.

-   <sup>--binary-upgrade</sup>

    <sup>Reserved for function extension. The option is not recommended.</sup>

-   <sup>--binary-upgrade-usermap="USER1=USER2"</sup>

    <sup>Reserved for function extension. The option is not recommended.</sup>

-   --non-lock-table

    This parameter is used only by the OM tool.

-   --tablespaces-postfix

    Reserved for function extension. The option is not recommended.

-   --parallel-jobs

    Specifies the number of concurrent backup processes. The value range is 1–1000.

-   --pipeline

    Uses a pipe to transmit the password. This parameter cannot be used on devices.


>![](public_sys-resources/icon-note.gif) **NOTE:** 
>-   The -g/--globals-only and -r/--roles-only parameters do not coexist.
>-   The  **-g/--globals-only**  and  **-t/--tablespaces-only**  parameters do not coexist.
>-   The -r/--roles-only and -t/--tablespaces-only parameters do not coexist.
>-   The -s/--schema-only and -a/--data-only parameters do not coexist.
>-   The -r/--roles-only and -a/--data-only parameters do not coexist.
>-   The -t/--tablespaces-only and -a/--data-only parameters do not coexist.
>-   The  **-g/--globals-only**  and** -a/--data-only parameters**  do not coexist.
>-   --tablespaces-postfix must be used with --binary-upgrade.
>-   --binary-upgrade-usermap must be used with --binary-upgrade.
>-   --parallel-jobs must be used with -f/--file.

Connection parameters:

-   -h, --host

    Specifies the host name. If the value begins with a slash \(/\), it is used as the directory for the Unix domain socket. The default value is taken from the PGHOST environment variable. If it is not set, a Unix domain socket connection is attempted.

    This parameter is valid only for the external database. For the local host in the database, only 127.0.0.1 can be used.

    Environment variable:  _PGHOST_

-   -l, --database

    Specifies the name of the database connected to dump all objects and discover other databases to be dumped. If this parameter is not specified, the postgres database will be used. If the postgres database does not exist, template1 will be used.

-   -p, --port

    Specifies the TCP port listened on by the server or the local Unix domain socket file name extension to ensure a correct connection. The default value is the PGPORT environment variable.

    If the thread pool is enabled, you are advised to use the pooler port, that is, the listening port number plus 1.

    Environment variable:  _PGPORT_

-   -U, --username

    Specifies the username for connection.

    Environment variable: PGUSER

-   -w, --no-password

    Never issues a password prompt. The connection attempt fails if the server requires password for authentication and the password is not provided in other ways. This parameter is useful in batch jobs and scripts in which no user password is required.

-   -W, --password

    Specifies the user password for connection. If the host uses the trust authentication policy, the administrator does not need to enter the -W option. If the -W option is not provided and you are not a system administrator, the Dump Restore tool will ask you to enter a password.

-   --role

    Specifies a role name to be used for creating the dump. If this option is selected, the  **SET ROLE**  command will be issued after the database is connected to  **gs\_dumpall**. It is useful when the authenticated user \(specified by  **-U**\) lacks the permissions required by  **gs\_dumpall**. It allows the user to switch to a role with the required permissions. Some installations have a policy against logging in directly as a system administrator. This option allows dumping data without violating the policy.

-   --rolepassword

    Specifies the password of the specific role.


## Description<a name="en-us_topic_0059778372_sc99dfbcba3eb44e59598baa7edd2d140"></a>

-   gs\_dumpall internally invokes gs\_dump. For details about the diagnosis information, see  [gs\_dump](gs_dump.md).
-   Once gs\_dumpall is restored, it is advised to run  **ANALYZE**  on each database so that the optimizer can provide useful statistics.
-   gs\_dumpall requires all needed tablespace directories to exit before the restoration. Otherwise, database creation will fail if the databases are in non-default locations.

## Example<a name="en-us_topic_0059778372_sb56721027dde49e1bf8c5df9685d2f2f"></a>

Use gs\_dumpall to export all databases at a time.

>![](public_sys-resources/icon-note.gif) **NOTE:** 
>gs\_dumpall supports only plain-text format export. Therefore, only gsql can be used to restore a file exported using gs\_dumpall.

```
gs_dumpall -f backup/bkp2.sql -p 37300
Password:
gs_dump[port='37300'][dbname='postgres'][2018-06-27 09:55:09]: The total objects number is 2371.
gs_dump[port='37300'][dbname='postgres'][2018-06-27 09:55:35]: [100.00%] 2371 objects have been dumped.
gs_dump[port='37300'][dbname='postgres'][2018-06-27 09:55:46]: dump database dbname='postgres' successfully
gs_dump[port='37300'][dbname='postgres'][2018-06-27 09:55:46]: total time: 55567  ms
gs_dumpall[port='37300'][2018-06-27 09:55:46]: dumpall operation successful
gs_dumpall[port='37300'][2018-06-27 09:55:46]: total time: 56088  ms
In the preceding command, backup/bkp2.sql indicates the exported file, and 37300 indicates the port number of the database server.
```

## Related Commands<a name="en-us_topic_0059778372_s9ed79eb3e2564786a6823616c460fc00"></a>

[gs\_dump](gs_dump.md)

