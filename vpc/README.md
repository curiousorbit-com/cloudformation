# Virtual Private Cloud (VPC) CloudFormation template
** NOTE: The templates in this repository will deploy resources in your AWS account,
which will result in usage charges. Always be sure that you understand what is in
any CloudFormation template before deploying into your AWS account.

## Default CIDR block
By default, the AWS CloudFormation template will create a VPC using a /16 CIDR 
block. This will provide for a total of 65,536 IP addresses.

The VPC CIDR block, will be further subdivided as follows. The default deployment
leaves plenty of space for future growth.

10.98.0.0/16:
    10.98.0.0/18 - AZ A
        10.98.0.0/19 - Private Subnet
        10.98.32.0/19
            10.98.32.0/20 - Public Subnet
            10.98.48.0/20
                10.98.48.0/21 - Protected Subnet
                10.98.56.0/21 - Spare
    10.98.64.0/18 - AZ B
        10.98.64.0/19 - Private Subnet
        10.98.96.0/19
            10.98.96.0/20 - Public Subnet
            10.98.112.0/20
                10.98.112.0/21 - Protected Subnet
                10.98.120.0/21 - Spare
    10.98.128.0/18 - Spare
    10.98.192.0/18 - Spare
