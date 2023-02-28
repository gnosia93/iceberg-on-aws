### Role Policy 추가 ###

The policy for Amazon EC2 Role to enable AWS Systems Manager service core functionality.



### 클러스터 생성 ###
[iceberg-conf.json]
```
[{
    "Classification":"iceberg-defaults",
    "Properties":{"iceberg.enabled":"true"}
}]
```

```
$ HOSTNAME=`hostname -s`
$ YMD=`date '+%Y-%m-%d'`
$ S3_BUCKET_NAME=iceberg-$HOSTNAME-$YMD

$ aws s3api create-bucket --bucket "$S3_BUCKET_NAME" --region ap-northeast-2 \
--create-bucket-configuration LocationConstraint=ap-northeast-2
{
    "Location": "http://iceberg-bcd07468d10a-2023-02-28.s3.amazonaws.com/"
}

$ aws emr create-cluster --release-label emr-6.6.0 \
--applications Name=Spark \
--configurations file://iceberg-conf.json \
--region ap-northeast-2 \
--name Iceberg \
--log-uri s3://$S3_BUCKET_NAME \
--instance-type m5.xlarge \
--instance-count 2 \
--service-role EMR_DefaultRole \
--ec2-attributes InstanceProfile=EMR_EC2_DefaultRole,KeyName=aws-kp,SubnetId=subnet-b35aa0d8
```



## 참고자료 ##
* https://aws.amazon.com/premiumsupport/knowledge-center/emr-failed-job-internal-error/
* https://aws.amazon.com/premiumsupport/knowledge-center/emr-default-role-invalid/
* https://codinghalbae.tistory.com/m/15
* https://aws.amazon.com/ko/premiumsupport/knowledge-center/emr-cluster-bootstrap-failed/
