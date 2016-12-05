# AWS Organizations

Sample OCPs for securing AWS Organizations:

| Service | Latency | Service Coverage | 
| ------- | ------- | ---------------- |
| CloudWatch Events | <1 minute | [Low](http://docs.aws.amazon.com/AmazonCloudWatch/latest/events/EventTypes.html)
| Config | Hourly Snapshots + ~minutely updates | [Medium](http://docs.aws.amazon.com/config/latest/developerguide/resource-config-reference.html) |
| Flowlogs | 10+ minutes | High |
| CloudTrail | 5–15 minutes | [High](http://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-supported-services.html) |

**Abbreviated OCP**
```json
{
  "Effect": "Deny",
  "Resource": "*",
  "Action": [
    "ec2:DeleteFlowLogs",
    "ec2:DeleteSubnet",
    "ec2:DeleteVpc",
    "rds:DeleteDBCluster",
    "redshift:DeleteCluster",
    "cloudtrail:DeleteTrail",
    "cloudtrail:StopLogging",
    "cloudtrail:UpdateTrail",
    "config:DeleteDeliveryChannel",
    "config:StopConfigurationRecorder",
    "events:DeleteRule",
    "events:DisableRule"
  ]
}
```

**Full Production OCP**
```json
{
  "Effect": "Deny",
  "Resource": "*",
  "Action": [
    "ec2:AcceptVpcPeeringConnection",
    "ec2:AssociateDhcpOptions",
    "ec2:AssociateRouteTable",
    "ec2:AttachInternetGateway",
    "ec2:AttachVpnGateway",
    "ec2:CreateNetworkAcl",
    "ec2:CreateNetworkAclEntry",
    "ec2:CreateRoute",
    "ec2:CreateRouteTable",
    "ec2:CreateSubnet",
    "ec2:CreateVpc",
    "ec2:CreateVpcEndpoint",
    "ec2:CreateVpcPeeringConnection",
    "ec2:CreateVpnConnection",
    "ec2:CreateVpnConnectionRoute",
    "ec2:CreateVpnGateway",
    "ec2:DeleteCustomerGateway",
    "ec2:DeleteDhcpOptions",
    "ec2:DeleteFlowLogs",
    "ec2:DeleteInternetGateway",
    "ec2:DeleteNatGateway",
    "ec2:DeleteNetworkAcl",
    "ec2:DeleteNetworkAclEntry",
    "ec2:DeleteNetworkInterface",
    "ec2:DeleteRoute",
    "ec2:DeleteRouteTable",
    "ec2:DeleteSubnet",
    "ec2:DeleteVpc",
    "ec2:DeleteVpcEndpoints",
    "ec2:DeleteVpcPeeringConnection",
    "ec2:DeleteVpnConnection",
    "ec2:DeleteVpnConnectionRoute",
    "ec2:DeleteVpnGateway",
    "ec2:ModifySubnetAttribute",
    "ec2:ModifyVpcAttribute",
    "ec2:ModifyVpcEndpoint",
    "ec2:ModifyVpcPeeringConnectionOptions",
    "ec2:ReplaceNetworkAclAssociation",
    "ec2:ReplaceNetworkAclEntry",
    "ec2:ReplaceRoute",
    "ec2:ReplaceRouteTableAssociation",
    "rds:DeleteDBClusterSnapshot",
    "rds:DeleteDBCluster",
    "rds:DeleteDBInstance",
    "rds:DeleteDBSnapshot",
    "redshift:DeleteCluster",
    "redshift:DeleteClusterSnapshot",
    "redshift:DeleteCluster",
    "cloudtrail:DeleteTrail",
    "cloudtrail:StopLogging",
    "cloudtrail:UpdateTrail",
    "config:DeleteDeliveryChannel",
    "config:StopConfigurationRecorder",
    "events:DeleteRule",
    "events:DisableRule"
  ]
}
```
