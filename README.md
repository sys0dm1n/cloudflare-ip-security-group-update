# cloudflare-ip-security-group-update
Lambda script to update CLoudFlare IP's into AWS security groups

AWS > Create function:

Runtime: Python 2.7

Role: Create a custom role


        {
            "Effect": "Allow",
            "Action": [
                "ec2:AuthorizeSecurityGroupIngress",
                "ec2:DescribeSecurityGroups"
            ],
            "Resource": [
                "*"
            ]
        }
    
Add trigger: CloudWatch Events

Set schedule to : Rate(1 day)

Paste the contents of cf-security-group-update.py

In the Environment variables section, add the following:

    key: SECURITY_GROUP_ID
    value: add your security group id here
    
    key: PORTS_LIST
    value: 80,443
    
   

