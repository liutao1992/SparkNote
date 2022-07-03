Spark SQL如何对接Hive
    场景：历史原因积累下来的，很多数据原先是采用Hive来进行处理的，
        现在想改用Spark来进行数据，我们必须要求Spark能够无缝对接已有的Hive的数据

        平滑的过渡

    操作是非常简单的，MetaStore
       Hive底层的元数据信息是存储在MySQL中  $HIVE_HOME/conf/hive-site.xml
       Spark若想访问Hive，则只需将`$HIVE_HOME/conf/hive-site.xml` 复制一份到 `$SPARK_HOME/conf/`目录即可

访问Hive：

```
spark-shell --jars driver/mysql-connector-java-5.1.41.jar 
```
> 也可以将jar包依赖放入`$SPARK_HOME/jars`目录下, 这样一来则不必在`spark-shell`脚本后面指定jar包依赖

Spark: Driver + Executor

我司的要求：使用到什么jar就加什么jar