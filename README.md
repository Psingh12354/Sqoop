# Sqoop

### passwrd
```
Welcome!12345
```
### load file from mysql to vm hdfs
-m 1 for primary key if it consist of primary key no need to use primary key provide distributed architecture
```
sqoop-import --connect jdbc:mysql://cdb22dw011.c0lf9xyp8cv9.ap-south-1.rds.amazonaws.com/cdb21dw011 --username cdb22dw011 -P --table StudentData --target-dir /StudentData1 -m 1
```


### Using select
```
sqoop-import --connect jdbc:mysql://cdb22dw011.c0lf9xyp8cv9.ap-south-1.rds.amazonaws.com/cdb21dw011 --username cdb22dw011 -P --table StudentData --where "gender='Female'" --target-dir /StudentDataFemale -m 1
```

### with primary key without -m 1 will create a distibute system
```
sqoop-import --connect jdbc:mysql://cdb22dw011.c0lf9xyp8cv9.ap-south-1.rds.amazonaws.com/cdb21dw011 --username cdb22dw011 -P --table demo --target-dir /demo123
```
### To access distribute system * for all
```
hadoop fs -cat /demo1/part*
or
hadoop fs -cat /demo1/part-m-0000
or 
hadoop fs -cat /demo1/part-m-0001
```