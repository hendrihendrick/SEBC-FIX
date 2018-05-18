Select web_logs
```

[root@ip-172-30-1-50 98-hdfs-DATANODE]# kinit groot
Password for groot@DODDYS.SG:
[root@ip-172-30-1-50 98-hdfs-DATANODE]# impala-shell
Starting Impala Shell without Kerberos authentication
Error connecting: TTransportException, TSocket read 0 bytes
Kerberos ticket found in the credentials cache, retrying the connection with a secure transport.
Connected to ip-172-30-1-50.ap-southeast-1.compute.internal:21000
Server version: impalad version 2.8.0-cdh5.11.2 RELEASE (build f89269c4b96da14a841e94bdf6d4d48821b0d658)
***********************************************************************************
Welcome to the Impala shell.
(Impala Shell v2.8.0-cdh5.11.2 (f89269c) built on Fri Aug 18 14:04:44 PDT 2017)

You can change the Impala daemon that you're connected to by using the CONNECT
command.To see how Impala will plan to run your query without actually executing
it, use the EXPLAIN command. You can change the level of detail in the EXPLAIN
output by setting the EXPLAIN_LEVEL query option.
***********************************************************************************
[ip-172-30-1-50.ap-southeast-1.compute.internal:21000] > select * from web_logs limit 10;
Query: select * from web_logs limit 10
Query submitted at: 2018-05-18 04:47:25 (Coordinator: http://ip-172-30-1-50.ap-southeast-1.compute.internal:25000)
Query progress can be monitored at: http://ip-172-30-1-50.ap-southeast-1.compute.internal:25000/query_plan?query_id=e040ef1fea146093:6cfecfa500000000
+---------------------+-----------+-------+---------------+-----------------+------+--------------+---------------+---------------+---------------+-----------+-------------------+--------------------+--------+-----------+----------+----------+--------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+--------+----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------+-----------------------------------------------------------+------------------+--------------------------------------+------------+
| _version_           | app       | bytes | city          | client_ip       | code | country_code | country_code3 | country_name  | device_family | extension | latitude          | longitude          | method | os_family | os_major | protocol | record | referer                                                                                                                                                                                    | region_code | request                                                                                                                                                                              | subapp | time                 | url                                                                                                                                                                     | user_agent                                                                     | user_agent_family                                         | user_agent_major | id                                   | date       |
+---------------------+-----------+-------+---------------+-----------------+------+--------------+---------------+---------------+---------------+-----------+-------------------+--------------------+--------+-----------+----------+----------+--------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+--------+----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------+-----------------------------------------------------------+------------------+--------------------------------------+------------+
| 1480895575515725824 | metastore | 1041  | Singapore     | 128.199.234.236 | 127  | SG           | SGP           | Singapore     | Other         |           | 1.293099999427795 | 103.8557968139648  | GET    | Other     |          | HTTP/1.1 |        | -                                                                                                                                                                                          | 0           | GET /metastore/table/default/sample_07 HTTP/1.1                                                                                                                                      | table  | 2014-05-04T06:35:49Z | /metastore/table/default/sample_07                                                                                                                                      | Mozilla/5.0 (compatible; phpservermon/3.0.1; +http://www.phpservermonitor.org) | Other                                                     |                  | 8836e6ce-9a21-449f-a372-9e57641389b3 | 2015-11-18 |
| 1480895575528308736 | metastore | 1041  | Singapore     | 128.199.234.236 | 127  | SG           | SGP           | Singapore     | Other         |           | 1.293099999427795 | 103.8557968139648  | GET    | Other     |          | HTTP/1.1 |        | -                                                                                                                                                                                          | 0           | GET /metastore/table/default/sample_07 HTTP/1.1                                                                                                                                      | table  | 2014-05-04T06:35:50Z | /metastore/table/default/sample_07                                                                                                                                      | Mozilla/5.0 (compatible; phpservermon/3.0.1; +http://www.phpservermonitor.org) | Other                                                     |                  | 6ddf6e38-7b83-423c-8873-39842dca2dbb | 2015-11-18 |
| 1480895575528308737 | search    | 1041  | Singapore     | 128.199.234.236 | 127  | SG           | SGP           | Singapore     | Other         |           | 1.293099999427795 | 103.8557968139648  | GET    | Other     |          | HTTP/1.1 |        | -                                                                                                                                                                                          | 0           | GET /search/?collection=10000001 HTTP/1.1                                                                                                                                            |        | 2014-05-04T06:35:52Z | /search/?collection=10000001                                                                                                                                            | Mozilla/5.0 (compatible; phpservermon/3.0.1; +http://www.phpservermonitor.org) | Other                                                     |                  | 313bb28e-dd7c-4364-a11e-9ffb0db7b303 | 2015-11-18 |
| 1480895575528308738 | search    | 1041  | Singapore     | 128.199.234.236 | 127  | SG           | SGP           | Singapore     | Other         |           | 1.293099999427795 | 103.8557968139648  | GET    | Other     |          | HTTP/1.1 |        | -                                                                                                                                                                                          | 0           | GET /search/?collection=10000001 HTTP/1.1                                                                                                                                            |        | 2014-05-04T06:35:53Z | /search/?collection=10000001                                                                                                                                            | Mozilla/5.0 (compatible; phpservermon/3.0.1; +http://www.phpservermonitor.org) | Other                                                     |                  | ecb47c61-a9e4-4b59-9234-04bd57695987 | 2015-11-18 |
| 1480895575528308739 |           | 238   | Singapore     | 128.199.234.236 | 127  | SG           | SGP           | Singapore     | Other         |           | 1.293099999427795 | 103.8557968139648  | HEAD   | Other     |          | HTTP/1.1 |        | -                                                                                                                                                                                          | 0           | HEAD / HTTP/1.1                                                                                                                                                                      |        | 2014-05-04T06:35:54Z | /                                                                                                                                                                       | Mozilla/5.0 (compatible; phpservermon/3.0.1; +http://www.phpservermonitor.org) | Other                                                     |                  | affdb6b9-3657-4d15-8af8-2ba2f3a69343 | 2015-11-18 |
| 1480895575528308740 | beeswax   | 1041  | Mountain View | 66.249.76.236   | 127  | US           | USA           | United States | Spider        |           | 37.38600158691406 | -122.0838012695312 | GET    | Other     |          | HTTP/1.1 |        | -                                                                                                                                                                                          | NULL        | GET /beeswax/query_history?q-type=beeswax&amp;q-user=dy8515s&amp;q-auto_query=off HTTP/1.1                                                                                           |        | 2014-05-04T06:35:54Z | /beeswax/query_history?q-type=beeswax&amp;q-user=dy8515s&amp;q-auto_query=off                                                                                           | Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)       | Googlebot                                                 | 2                | e3f88d9e-7e5b-4ef7-8941-c0d83720616c | 2015-11-18 |
| 1480895575528308741 |           | 1041  | Guiyang       | 222.85.131.87   | 127  | CN           | CHN           | China         | Other         |           | 26.58329963684082 | 106.7166976928711  | GET    | Windows 7 |          | HTTP/1.1 |        | -                                                                                                                                                                                          | 18          | GET / HTTP/1.1                                                                                                                                                                       |        | 2014-05-04T06:35:55Z | /                                                                                                                                                                       | Mozilla/5.0 (compatible; MSIE 10.0; Windows NT 6.1; Trident/6.0)               | IE                                                        | 10               | 4dbb1f74-6856-4fe3-8515-c53eab600b60 | 2015-11-18 |
| 1480895575529357312 | desktop   | 0     | Guiyang       | 222.85.131.87   | 127  | CN           | CHN           | China         | Other         |           | 26.58329963684082 | 106.7166976928711  |        | Other     |          |          |        | -                                                                                                                                                                                          | 18          | -                                                                                                                                                                                    |        | 2014-05-04T06:36:16Z |                                                                                                                                                                         | -                                                                              | Other                                                     |                  | 86cdb56d-99c0-4701-a842-472741bb833a | 2015-11-18 |
| 1480895575529357313 | search    | 1041  | Shanghai      | 101.226.168.225 | 127  | CN           | CHN           | China         | Other         |           | 31.04560089111328 | 121.3996963500977  | GET    | Windows 7 |          | HTTP/1.1 |        | http://demo.gethue.com/search/?collection=10000001&amp;fq=%7Cuser_statuses_count%3A%5B%229000%22%20TO%20%229999%22%5D%7Cuser_location%3A%22new%20york%22&amp;query&amp;rows=15&amp;start=0 | 23          | GET /search/?collection=10000001&amp;fq=%7Cuser_statuses_count%3A%5B%229000%22%20TO%20%229999%22%5D%7Cuser_location%3A%22new%20york%22&amp;query&amp;rows=15&amp;start=0 HTTP/1.1    |        | 2014-05-04T06:38:31Z | /search/?collection=10000001&amp;fq=%7Cuser_statuses_count%3A%5B%229000%22%20TO%20%229999%22%5D%7Cuser_location%3A%22new%20york%22&amp;query&amp;rows=15&amp;start=0    | "Mozilla/5.0 (Windows NT 6.1) AppleWebKit/537.1 (KHTML                         |  like Gecko) Chrome/21.0.1180.89 Safari/537.1; 360Spider" | Chrome           | 21                                   | 2015-11-18 |
| 1480895575529357314 | search    | 1041  | Mountain View | 66.249.76.225   | 127  | US           | USA           | United States | Spider        |           | 37.38600158691406 | -122.0838012695312 | GET    | Other     |          | HTTP/1.1 |        | -                                                                                                                                                                                          | NULL        | GET /search/?collection=10000001&amp;query=&amp;fq=%7Cuser_followers_count%3A%5B%22100%22%20TO%20%22199%22%5D%7Cuser_location%3A%22philippines%22&amp;rows=15&amp;start=240 HTTP/1.1 |        | 2014-05-04T06:38:55Z | /search/?collection=10000001&amp;query=&amp;fq=%7Cuser_followers_count%3A%5B%22100%22%20TO%20%22199%22%5D%7Cuser_location%3A%22philippines%22&amp;rows=15&amp;start=240 | Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)       | Googlebot                                                 | 2                | 8260ca42-55d6-4cd4-8beb-8767826dc929 | 2015-11-18 |
+---------------------+-----------+-------+---------------+-----------------+------+--------------+---------------+---------------+---------------+-----------+-------------------+--------------------+--------+-----------+----------+----------+--------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+--------+----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------+-----------------------------------------------------------+------------------+--------------------------------------+------------+
WARNINGS: Error converting column: 19 to BIGINT
Error parsing row: file: hdfs://ip-172-30-1-139.ap-southeast-1.compute.internal:8020/user/doddys/2015_11_18/web_logs_1.csv, before offset: 115714
Error converting column: 19 to BIGINT
Error parsing row: file: hdfs://ip-172-30-1-139.ap-southeast-1.compute.internal:8020/user/doddys/2015_11_18/web_logs_1.csv, before offset: 115714

Fetched 10 row(s) in 0.38s


```

Select customer

```
Fetched 10 row(s) in 0.38s
[ip-172-30-1-50.ap-southeast-1.compute.internal:21000] > select * from customers limit 10;
Query: select * from customers limit 10
Query submitted at: 2018-05-18 04:48:40 (Coordinator: http://ip-172-30-1-50.ap-southeast-1.compute.internal:25000)
Query progress can be monitored at: http://ip-172-30-1-50.ap-southeast-1.compute.internal:25000/query_plan?query_id=17413088c0655861:e91c16d100000000
+-------+---------------------+
| id    | name                |
+-------+---------------------+
| 75012 | Dorothy Wilk        |
| 17254 | Martin Johnson      |
| 12532 | Melvin Garcia       |
| 42632 | Raymond S. Vestal   |
| 77913 | Betty J. Giambrone  |
| 38807 | Rebecca T. Johnson  |
| 71843 | David B. Allison    |
| 67099 | Jay N. Weaver       |
| 83510 | Carol B. Houser     |
| 48072 | Octaviana Guiterrez |
+-------+---------------------+
Fetched 10 row(s) in 5.00s

```