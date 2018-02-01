# AWS-t2.xlarge-setup

This script will configure cost effective AWS t2.xlarge instance for deeplarning practice. Script reduce Ebs volume size from 128 to 30.

If you already have existing t2.xlarge script, add first line and replace second with existing similar line. OR download full script file.

```sh
export ami="ami-9c54f4fc"  # In this case region is Oregon, do the needful changes according to your region
export instanceId=`aws ec2 run-instances --image-id $ami --count 1 --instance-type t2.xlarge --key-name aws-key-$name --security-group-ids $securityGroupId --subnet-id $subnetId --associate-public-ip-address --block-device-mapping "[ { \"DeviceName\": \"/dev/sda1\", \"Ebs\": { \"VolumeSize\": 30, \"VolumeType\": \"gp2\" } } ]" --query 'Instances[0].InstanceId' --output text`
```
