
[iceberg-conf.json]
```
[{
    "Classification":"iceberg-defaults",
    "Properties":{"iceberg.enabled":"true"}
}]
```

```
$ aws emr create-cluster --release-label emr-6.5.0 \
--applications Name=Spark \
--configurations file://iceberg-conf.json \
--region ap-northeast-2 \
--name Iceberg-Cluster \
--log-uri s3://iceberg-seoul-20230225/ \
--instance-type m5.xlarge \
--instance-count 2 \
--service-role EMR_DefaultRole_V2 \ 
--ec2-attributes InstanceProfile=EMR_EC2_DefaultRole,SubnetId=subnet-b35aa0d8
```
