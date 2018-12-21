# 开源数据同步工具——datax

github地址：https://github.com/alibaba/DataX

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
chcp 65001
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

