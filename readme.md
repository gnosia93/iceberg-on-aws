Apache Iceberg is an open table format for huge analytic datasets.
Iceberg adds tables to compute engines including Spark, Trino, PrestoDB, Flink, Hive and Impala using a high-performance table format that works just like a SQL table.

* Schema evolution supports add, drop, update, or rename, and has no side-effects
* Hidden partitioning prevents user mistakes that cause silently incorrect results or extremely slow queries
* Partition layout evolution can update the layout of a table as data volume or query patterns change
* Time travel enables reproducible queries that use exactly the same table snapshot, or lets users easily examine changes
* Version rollback allows users to quickly correct problems by resetting tables to a good state

------------

* [EMR 클러스터 생성](https://github.com/gnosia93/iceberg-on-aws/blob/main/tutorial/emr-create.md)


## 스파크 튜닝 ##

* [Executor 사이즈와 개수 정하기](https://jaemunbro.medium.com/spark-executor-%EA%B0%9C%EC%88%98-%EC%A0%95%ED%95%98%EA%B8%B0-b9f0e0cc1fd8)


## 참고자료 ##
* [빅데이터 - 스칼라(scala), 스파크(spark)로 시작하기](https://wikidocs.net/book/2350)
* [스파크 어플리케이션 튜닝](http://kysepark.blogspot.com/2016/04/how-to-tune-your-apache-spark-jobs-part.html)
* [스파크 성능 튜닝](https://pizzathief.oopy.io/dealing-with-spark-data-skew)
* https://datacook.tistory.com/81
* https://datacook.tistory.com/80
* https://aws.amazon.com/blogs/big-data/build-an-apache-iceberg-data-lake-using-amazon-athena-amazon-emr-and-aws-glue/
* https://iceberg.apache.org/
