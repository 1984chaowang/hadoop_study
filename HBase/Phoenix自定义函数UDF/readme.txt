phoenix �Զ��庯��UDF-����
201906041152,001|201906041155,002|...
ʱ��,����

����: ����1:201906041152,001|201906041155,002|... �ַ��� ����2: 201906040000-201906042359
	�ж��Ƿ��ڲ���2��Χ
�ж�: 201906041152,001|201906041155,002|... �ַ���
���0,001,2,002
1:�̳�ScalarFunction�� ʵ���Զ��庯�� ���
2:�ϴ���hdfs��
3:CREATE FUNCTION judgeTrackTime(varchar) returns varchar as 'com.enjoyor.mtdap.UDFS.PhoenixUdfDemo' using jar 'hdfs://hacluster/MTDAP/UDF/PhoenixUDF.jar'

hdfs�ϴ�:hdfs dfs -put file:/opt/PhoenixUDF.jar hdfs://hacluster/MTDAP/UDF/
�鿴�ļ�:hadoop fs -ls hdfs://hacluster/MTDAP/UDF
ɾ���ļ�:hadoop fs -rm  hdfs://hacluster/MTDAP/UDF/PhoenixUDF.jar

------------------------------------------------------------------------
����������ļ��ͷ���˶���Ҫ���һ������
<property>
  <name>phoenix.functions.allowUserDefinedFunctions</name>
  <value>true</value>
</property>
<property>
  <name>fs.hdfs.impl</name>
  <value>org.apache.hadoop.hdfs.DistributedFileSystem</value>
</property>
<property>
  <name>hbase.dynamic.jars.dir</name>
  <value>hdfs://hacluster/MTDAP/UDF</value>
</property>



�쳣:�������������
��:User defined functions are configured to not be allowed. To allow configure phoenix.functions.allowUserDefinedFunctions to true.