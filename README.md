# terraform-aws-jenkins

## Usage

```
module "ec2-jenkins" {
    source                    = "git::https://github.com/tothenew/terraform-aws-jenkins.git"
    key_name                  = "key_name"
    iam_instance_profile      = "test-role"
    security_groups           = ["sg-999999999999"]
    subnet_id                 = "subnet-999999999999"
    project_name_prefix       = "dev-tothenew"
    common_tags               = {
      "Project"     = "ToTheNew",
      "Environment" = "dev"
    }
}
```

<!--- BEGIN_TF_DOCS --->

## Requirements

No requirements.

## Providers

| Name | Version |
|------|---------|
| aws | n/a |
| template | n/a |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| common\_tags | A mapping of tags to assign to the resource | `map(string)` | n/a | yes |
| delete\_on\_termination | Whether EBS volume will be deleted when instance gets deleted. | `bool` | `true` | no |
| disable\_api\_stop | If true, enables EC2 Instance Stop Protection. | `bool` | `false` | no |
| disable\_api\_termination | If true, enables EC2 Instance Termination Protection | `bool` | `true` | no |
| ebs\_optimized | If true, the launched EC2 instance will be EBS-optimized | `bool` | `true` | no |
| encrypted | Whether EBS volume will be encrypted. | `bool` | `true` | no |
| iam\_instance\_profile | IAM Instance Profile to launch the instance with. Specified as the name of the Instance Profile | `string` | n/a | yes |
| instance\_type | The type of instance to start | `string` | `"t3a.medium"` | no |
| key\_name | Key name of the Key Pair to use for the instance; which can be managed using the `aws_key_pair` resource | `string` | n/a | yes |
| project\_name\_prefix | A string value to describe prefix of all the resources | `string` | `"dev-tothenew"` | no |
| root\_volume\_size | Root volume size of the EC2 instance | `number` | `100` | no |
| security\_groups | A string value for Security Group ID | `list(string)` | n/a | yes |
| source\_dest\_check | Source destination Check. Used for NAT or VPNs. | `bool` | `true` | no |
| subnet\_id | The VPC Subnet IDs to launch in | `string` | n/a | yes |
| volume\_type | Volume type for EC2 instance default latest type | `string` | `"gp3"` | no |

## Outputs

| Name | Description |
|------|-------------|
| arn | n/a |
| id | n/a |
| private\_ip | n/a |
| public\_ip | n/a |

<!--- END_TF_DOCS --->