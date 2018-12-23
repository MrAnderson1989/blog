# 开源数据同步工具——datax

DataX 是阿里巴巴集团内被广泛使用的离线数据同步工具/平台，实现包括 MySQL、Oracle、SqlServer、Postgre、HDFS、Hive、ADS、HBase、TableStore(OTS)、MaxCompute(ODPS)、DRDS 等各种异构数据源之间高效的数据同步功能。


github地址：https://github.com/alibaba/DataX

## 支持的数据存储

| 类型           | 数据源        | Reader(读) | Writer(写) |文档|
| ------------ | ---------- | :-------: | :-------: |:-------: |
| RDBMS 关系型数据库 | MySQL      |     √     |     √     |[读](https://github.com/alibaba/DataX/blob/master/mysqlreader/doc/mysqlreader.md) 、[写](https://github.com/alibaba/DataX/blob/master/mysqlwriter/doc/mysqlwriter.md)|
|              | Oracle     |     √     |     √     |[读](https://github.com/alibaba/DataX/blob/master/oraclereader/doc/oraclereader.md) 、[写](https://github.com/alibaba/DataX/blob/master/oraclewriter/doc/oraclewriter.md)|
|              | SQLServer  |     √     |     √     |[读](https://github.com/alibaba/DataX/blob/master/sqlserverreader/doc/sqlserverreader.md) 、[写](https://github.com/alibaba/DataX/blob/master/sqlserverwriter/doc/sqlserverwriter.md)|
|              | PostgreSQL |     √     |     √     |[读](https://github.com/alibaba/DataX/blob/master/postgresqlreader/doc/postgresqlreader.md) 、[写](https://github.com/alibaba/DataX/blob/master/postgresqlwriter/doc/postgresqlwriter.md)|
|              | DRDS |     √     |     √     |[读](https://github.com/alibaba/DataX/blob/master/drdsreader/doc/drdsreader.md) 、[写](https://github.com/alibaba/DataX/blob/master/drdswriter/doc/drdswriter.md)|
|              | 通用RDBMS(支持所有关系型数据库)         |     √     |     √     |[读](https://github.com/alibaba/DataX/blob/master/rdbmsreader/doc/rdbmsreader.md) 、[写](https://github.com/alibaba/DataX/blob/master/rdbmswriter/doc/rdbmswriter.md)|
| 阿里云数仓数据存储    | ODPS       |     √     |     √     |[读](https://github.com/alibaba/DataX/blob/master/odpsreader/doc/odpsreader.md) 、[写](https://github.com/alibaba/DataX/blob/master/odpswriter/doc/odpswriter.md)|
|              | ADS        |           |     √     |[写](https://github.com/alibaba/DataX/blob/master/adswriter/doc/adswriter.md)|
|              | OSS        |     √     |     √     |[读](https://github.com/alibaba/DataX/blob/master/ossreader/doc/ossreader.md) 、[写](https://github.com/alibaba/DataX/blob/master/osswriter/doc/osswriter.md)|
|              | OCS        |     √     |     √     |[读](https://github.com/alibaba/DataX/blob/master/ocsreader/doc/ocsreader.md) 、[写](https://github.com/alibaba/DataX/blob/master/ocswriter/doc/ocswriter.md)|
| NoSQL数据存储    | OTS        |     √     |     √     |[读](https://github.com/alibaba/DataX/blob/master/otsreader/doc/otsreader.md) 、[写](https://github.com/alibaba/DataX/blob/master/otswriter/doc/otswriter.md)|
|              | Hbase0.94  |     √     |     √     |[读](https://github.com/alibaba/DataX/blob/master/hbase094xreader/doc/hbase094xreader.md) 、[写](https://github.com/alibaba/DataX/blob/master/hbase094xwriter/doc/hbase094xwriter.md)|
|              | Hbase1.1   |     √     |     √     |[读](https://github.com/alibaba/DataX/blob/master/hbase11xreader/doc/hbase11xreader.md) 、[写](https://github.com/alibaba/DataX/blob/master/hbase11xwriter/doc/hbase11xwriter.md)|
|              | Phoenix4.x   |     √     |     √     |[读](https://github.com/alibaba/DataX/blob/master/hbase11xsqlreader/doc/hbase11xsqlreader.md) 、[写](https://github.com/alibaba/DataX/blob/master/hbase11xsqlwriter/doc/hbase11xsqlwriter.md)|
|              | MongoDB    |     √     |     √     |[读](https://github.com/alibaba/DataX/blob/master/mongoreader/doc/mongoreader.md) 、[写](https://github.com/alibaba/DataX/blob/master/mongowriter/doc/mongowriter.md)|
|              | Hive       |     √     |     √     |[读](https://github.com/alibaba/DataX/blob/master/hdfsreader/doc/hdfsreader.md) 、[写](https://github.com/alibaba/DataX/blob/master/hdfswriter/doc/hdfswriter.md)|
| 无结构化数据存储     | TxtFile    |     √     |     √     |[读](https://github.com/alibaba/DataX/blob/master/txtfilereader/doc/txtfilereader.md) 、[写](https://github.com/alibaba/DataX/blob/master/txtfilewriter/doc/txtfilewriter.md)|
|              | FTP        |     √     |     √     |[读](https://github.com/alibaba/DataX/blob/master/ftpreader/doc/ftpreader.md) 、[写](https://github.com/alibaba/DataX/blob/master/ftpwriter/doc/ftpwriter.md)|
|              | HDFS       |     √     |     √     |[读](https://github.com/alibaba/DataX/blob/master/hdfsreader/doc/hdfsreader.md) 、[写](https://github.com/alibaba/DataX/blob/master/hdfswriter/doc/hdfswriter.md)|
|              | Elasticsearch       |         |     √     |[写](https://github.com/alibaba/DataX/blob/master/elasticsearchwriter/doc/elasticsearchwriter.md)|


## 环境依赖

- JDK(1.6以上，推荐1.6)
- Python(推荐Python2.6.x)
- datax

## 使用方法

脚本文件：run.bat 
任务文件：job/myjob.json 
job/t_org_dept.json 
job/t_org_user.json

```

chcp 65001 # 防止中文乱码
e:
cd E:\Application\datax
python2 bin\datax.py -p "-Dtable=T_ORG_VIEW_TYPE" job\myjob.json
python2 bin\datax.py -p "-Dtable=T_ORG_TEX_CLASSIFY" job\myjob.json
python2 bin\datax.py -p "-Dtable=T_ORG_DEPT_GROUP" job\myjob.json
python2 bin\datax.py -p "-Dtable=T_ORG_DEPT_LEVEL_TYPE" job\myjob.json
python2 bin\datax.py -p "-Dtable=T_ORG_DEPT" job\t_org_dept.json
python2 bin\datax.py -p "-Dtable=T_ORG_FUNCTION_TYPE" job\myjob.json
python2 bin\datax.py -p "-Dtable=T_ORG_USER" job\t_org_user.json
python2 bin\datax.py -p "-Dtable=T_ORG_ROLE_GROUP" job\myjob.json
python2 bin\datax.py -p "-Dtable=T_ORG_ROLE" job\myjob.json
python2 bin\datax.py -p "-Dtable=T_ORG_USER_REL" job\myjob.json
python2 bin\datax.py -p "-Dtable=T_ORG_DEPT_BIZ_TYPE" job\myjob.json
python2 bin\datax.py -p "-Dtable=T_ORG_BIZ_RELATION_TYPE" job\myjob.json
python2 bin\datax.py -p "-Dtable=T_ORG_CUD_DEPT" job\myjob.json
python2 bin\datax.py -p "-Dtable=T_ORG_CUD_DEPT_CHG" job\myjob.json
python2 bin\datax.py -p "-Dtable=T_ORG_CUU_GROUP" job\myjob.json
python2 bin\datax.py -p "-Dtable=T_ORG_CUU_GROUP_CHG" job\myjob.json
python2 bin\datax.py -p "-Dtable=T_ORG_CUU_GROUP_CHG" job\myjob.json
python2 bin\datax.py -p "-Dtable=T_ORG_CUU_USER_CHG" job\myjob.json
python2 bin\datax.py -p "-Dtable=T_ORG_DEPT_BIZ_REL_INDEX" job\myjob.json
python2 bin\datax.py -p "-Dtable=T_ORG_DEPT_BIZ_RELATION" job\myjob.json
python2 bin\datax.py -p "-Dtable=T_ORG_DEPT_BIZ_TYPE_REL" job\myjob.json
python2 bin\datax.py -p "-Dtable=T_ORG_DEPT_HISTORY" job\myjob.json
python2 bin\datax.py -p "-Dtable=T_ORG_DEPT_LEVEL_TYPE_REL" job\myjob.json
python2 bin\datax.py -p "-Dtable=T_ORG_DEPT_REL" job\myjob.json
python2 bin\datax.py -p "-Dtable=T_ORG_DEPT_UNIT" job\myjob.json
python2 bin\datax.py -p "-Dtable=T_ORG_DEPT_USAGE" job\myjob.json
python2 bin\datax.py -p "-Dtable=T_ORG_ENTRUST" job\myjob.json
python2 bin\datax.py -p "-Dtable=T_ORG_EXPORT_IMPORT_MODEL" job\myjob.json
python2 bin\datax.py -p "-Dtable=T_ORG_IMPORT_DEPT" job\myjob.json
python2 bin\datax.py -p "-Dtable=T_ORG_IMPORT_TASK" job\myjob.json
python2 bin\datax.py -p "-Dtable=T_ORG_IMPORT_USER" job\myjob.json
python2 bin\datax.py -p "-Dtable=T_ORG_INCHARGE_TYPE" job\myjob.json
python2 bin\datax.py -p "-Dtable=T_ORG_PARAMETERS" job\myjob.json
python2 bin\datax.py -p "-Dtable=T_ORG_POST_TYPE" job\myjob.json
python2 bin\datax.py -p "-Dtable=T_ORG_POST_TYPE_REL" job\myjob.json
python2 bin\datax.py -p "-Dtable=T_ORG_ROLE_ATTR_BIZ_TYPE" job\myjob.json
python2 bin\datax.py -p "-Dtable=T_ORG_ROLE_ATTR_FUNCTION_TYPE" job\myjob.json
python2 bin\datax.py -p "-Dtable=T_ORG_ROLE_ATTR_IS_LEADER" job\myjob.json
python2 bin\datax.py -p "-Dtable=T_ORG_ROLE_ATTR_IS_MAINREL" job\myjob.json
python2 bin\datax.py -p "-Dtable=T_ORG_ROLE_ATTR_LEVEL_TYPE" job\myjob.json
python2 bin\datax.py -p "-Dtable=T_ORG_ROLE_ATTR_POST_TYPE" job\myjob.json
python2 bin\datax.py -p "-Dtable=T_ORG_ROLE_ATTR_USER_SEX" job\myjob.json
python2 bin\datax.py -p "-Dtable=T_ORG_ROLE_CACHE_DEPT" job\myjob.json
python2 bin\datax.py -p "-Dtable=T_ORG_ROLE_CACHE_USER" job\myjob.json
python2 bin\datax.py -p "-Dtable=T_ORG_ROLE_GROUP_REL" job\myjob.json
python2 bin\datax.py -p "-Dtable=T_ORG_ROLE_MODULE_REL" job\myjob.json
python2 bin\datax.py -p "-Dtable=T_ORG_SYNC_DISPOSER_INFO" job\myjob.json
python2 bin\datax.py -p "-Dtable=T_ORG_TEX_DATA_SYNC_STATUS" job\myjob.json
python2 bin\datax.py -p "-Dtable=T_ORG_TEX_DATA_TARGET" job\myjob.json
python2 bin\datax.py -p "-Dtable=T_ORG_TEX_DEPT_GROUP" job\myjob.json
python2 bin\datax.py -p "-Dtable=T_ORG_TEX_DEPT" job\myjob.json
python2 bin\datax.py -p "-Dtable=T_ORG_TEX_UNIT_CHANGE_LOG" job\myjob.json
python2 bin\datax.py -p "-Dtable=T_ORG_TEX_USER" job\myjob.json
python2 bin\datax.py -p "-Dtable=T_ORG_TEX_USER_REL" job\myjob.json
python2 bin\datax.py -p "-Dtable=T_ORG_TRUST_DATA_STATUS" job\myjob.json
python2 bin\datax.py -p "-Dtable=T_ORG_TRUST_DATA_SYNC_DISPOSER" job\myjob.json
python2 bin\datax.py -p "-Dtable=T_ORG_TRUST_ORG" job\myjob.json
python2 bin\datax.py -p "-Dtable=T_ORG_UNIT_CHANGE_LOG" job\myjob.json
python2 bin\datax.py -p "-Dtable=T_ORG_USER_CERT" job\myjob.json
python2 bin\datax.py -p "-Dtable=T_ORG_USER_CONTACT" job\myjob.json
python2 bin\datax.py -p "-Dtable=T_ORG_USER_HR_LITE" job\myjob.json
python2 bin\datax.py -p "-Dtable=T_ORG_USER_IDENTITY" job\myjob.json
python2 bin\datax.py -p "-Dtable=T_ORG_USER_IDENTITY_HISTORY" job\myjob.json
python2 bin\datax.py -p "-Dtable=T_ORG_USER_INCHARGE" job\myjob.json
python2 bin\datax.py -p "-Dtable=T_ORG_USER_REL_HISTORY" job\myjob.json
python2 bin\datax.py -p "-Dtable=T_TEX_CENTER" job\myjob.json
python2 bin\datax.py -p "-Dtable=T_TEX_PLATFORM" job\myjob.json
python2 bin\datax.py -p "-Dtable=T_TEX_RELATION" job\myjob.json

```

