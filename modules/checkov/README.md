
       _               _
   ___| |__   ___  ___| | _______   __
  / __| '_ \ / _ \/ __| |/ / _ \ \ / /
 | (__| | | |  __/ (__|   < (_) \ V /
  \___|_| |_|\___|\___|_|\_\___/ \_/

By Prisma Cloud | version: 3.2.458 

terraform scan results:

Passed checks: 1, Failed checks: 7, Skipped checks: 0

Check: CKV_AWS_41: "Ensure no hard coded AWS access key and secret key exists in provider"
	PASSED for resource: aws.default
	File: \main.tf:1-3
	Guide: [1mhttps://docs.prismacloud.io/en/enterprise-edition/policy-reference/aws-policies/secrets-policies/bc-aws-secrets-5
[0mCheck: CKV_AWS_23: "Ensure every security group and rule has a description"
	FAILED for resource: aws_security_group.insecure_sg
	File: \main.tf:4-19
	Guide: [1mhttps://docs.prismacloud.io/en/enterprise-edition/policy-reference/aws-policies/aws-networking-policies/networking-31
[0m
		[37m4  | [33mresource "aws_security_group" "insecure_sg" {
		[37m5  | [33m  name        = "allow_all"
		[37m6  | [33m  description = "Allow all inbound traffic"
		[37m7  | [33m  ingress {
		[37m8  | [33m    from_port   = 0
		[37m9  | [33m    to_port     = 0
		[37m10 | [33m    protocol    = "-1"
		[37m11 | [33m    cidr_blocks = ["0.0.0.0/0"]
		[37m12 | [33m  }
		[37m13 | [33m  egress {
		[37m14 | [33m    from_port   = 0
		[37m15 | [33m    to_port     = 0
		[37m16 | [33m    protocol    = "-1"
		[37m17 | [33m    cidr_blocks = ["0.0.0.0/0"]
		[37m18 | [33m  }
		[37m19 | [33m}

Check: CKV_AWS_382: "Ensure no security groups allow egress from 0.0.0.0:0 to port -1"
	FAILED for resource: aws_security_group.insecure_sg
	File: \main.tf:4-19
	Guide: [1mhttps://docs.prismacloud.io/en/enterprise-edition/policy-reference/aws-policies/aws-networking-policies/bc-aws-382
[0m
		[37m4  | [33mresource "aws_security_group" "insecure_sg" {
		[37m5  | [33m  name        = "allow_all"
		[37m6  | [33m  description = "Allow all inbound traffic"
		[37m7  | [33m  ingress {
		[37m8  | [33m    from_port   = 0
		[37m9  | [33m    to_port     = 0
		[37m10 | [33m    protocol    = "-1"
		[37m11 | [33m    cidr_blocks = ["0.0.0.0/0"]
		[37m12 | [33m  }
		[37m13 | [33m  egress {
		[37m14 | [33m    from_port   = 0
		[37m15 | [33m    to_port     = 0
		[37m16 | [33m    protocol    = "-1"
		[37m17 | [33m    cidr_blocks = ["0.0.0.0/0"]
		[37m18 | [33m  }
		[37m19 | [33m}

Check: CKV_AWS_24: "Ensure no security groups allow ingress from 0.0.0.0:0 to port 22"
	FAILED for resource: aws_security_group.insecure_sg
	File: \main.tf:4-19
	Guide: [1mhttps://docs.prismacloud.io/en/enterprise-edition/policy-reference/aws-policies/aws-networking-policies/networking-1-port-security
[0m
		[37m4  | [33mresource "aws_security_group" "insecure_sg" {
		[37m5  | [33m  name        = "allow_all"
		[37m6  | [33m  description = "Allow all inbound traffic"
		[37m7  | [33m  ingress {
		[37m8  | [33m    from_port   = 0
		[37m9  | [33m    to_port     = 0
		[37m10 | [33m    protocol    = "-1"
		[37m11 | [33m    cidr_blocks = ["0.0.0.0/0"]
		[37m12 | [33m  }
		[37m13 | [33m  egress {
		[37m14 | [33m    from_port   = 0
		[37m15 | [33m    to_port     = 0
		[37m16 | [33m    protocol    = "-1"
		[37m17 | [33m    cidr_blocks = ["0.0.0.0/0"]
		[37m18 | [33m  }
		[37m19 | [33m}

Check: CKV_AWS_25: "Ensure no security groups allow ingress from 0.0.0.0:0 to port 3389"
	FAILED for resource: aws_security_group.insecure_sg
	File: \main.tf:4-19
	Guide: [1mhttps://docs.prismacloud.io/en/enterprise-edition/policy-reference/aws-policies/aws-networking-policies/networking-2
[0m
		[37m4  | [33mresource "aws_security_group" "insecure_sg" {
		[37m5  | [33m  name        = "allow_all"
		[37m6  | [33m  description = "Allow all inbound traffic"
		[37m7  | [33m  ingress {
		[37m8  | [33m    from_port   = 0
		[37m9  | [33m    to_port     = 0
		[37m10 | [33m    protocol    = "-1"
		[37m11 | [33m    cidr_blocks = ["0.0.0.0/0"]
		[37m12 | [33m  }
		[37m13 | [33m  egress {
		[37m14 | [33m    from_port   = 0
		[37m15 | [33m    to_port     = 0
		[37m16 | [33m    protocol    = "-1"
		[37m17 | [33m    cidr_blocks = ["0.0.0.0/0"]
		[37m18 | [33m  }
		[37m19 | [33m}

Check: CKV_AWS_260: "Ensure no security groups allow ingress from 0.0.0.0:0 to port 80"
	FAILED for resource: aws_security_group.insecure_sg
	File: \main.tf:4-19
	Guide: [1mhttps://docs.prismacloud.io/en/enterprise-edition/policy-reference/aws-policies/aws-networking-policies/ensure-aws-security-groups-do-not-allow-ingress-from-00000-to-port-80
[0m
		[37m4  | [33mresource "aws_security_group" "insecure_sg" {
		[37m5  | [33m  name        = "allow_all"
		[37m6  | [33m  description = "Allow all inbound traffic"
		[37m7  | [33m  ingress {
		[37m8  | [33m    from_port   = 0
		[37m9  | [33m    to_port     = 0
		[37m10 | [33m    protocol    = "-1"
		[37m11 | [33m    cidr_blocks = ["0.0.0.0/0"]
		[37m12 | [33m  }
		[37m13 | [33m  egress {
		[37m14 | [33m    from_port   = 0
		[37m15 | [33m    to_port     = 0
		[37m16 | [33m    protocol    = "-1"
		[37m17 | [33m    cidr_blocks = ["0.0.0.0/0"]
		[37m18 | [33m  }
		[37m19 | [33m}

Check: CKV_AWS_277: "Ensure no security groups allow ingress from 0.0.0.0:0 to port -1"
	FAILED for resource: aws_security_group.insecure_sg
	File: \main.tf:4-19
	Guide: [1mhttps://docs.prismacloud.io/en/enterprise-edition/policy-reference/aws-policies/aws-networking-policies/ensure-aws-security-group-does-not-allow-all-traffic-on-all-ports
[0m
		[37m4  | [33mresource "aws_security_group" "insecure_sg" {
		[37m5  | [33m  name        = "allow_all"
		[37m6  | [33m  description = "Allow all inbound traffic"
		[37m7  | [33m  ingress {
		[37m8  | [33m    from_port   = 0
		[37m9  | [33m    to_port     = 0
		[37m10 | [33m    protocol    = "-1"
		[37m11 | [33m    cidr_blocks = ["0.0.0.0/0"]
		[37m12 | [33m  }
		[37m13 | [33m  egress {
		[37m14 | [33m    from_port   = 0
		[37m15 | [33m    to_port     = 0
		[37m16 | [33m    protocol    = "-1"
		[37m17 | [33m    cidr_blocks = ["0.0.0.0/0"]
		[37m18 | [33m  }
		[37m19 | [33m}

Check: CKV2_AWS_5: "Ensure that Security Groups are attached to another resource"
	FAILED for resource: aws_security_group.insecure_sg
	File: \main.tf:4-19
	Guide: [1mhttps://docs.prismacloud.io/en/enterprise-edition/policy-reference/aws-policies/aws-networking-policies/ensure-that-security-groups-are-attached-to-ec2-instances-or-elastic-network-interfaces-enis
[0m
		[37m4  | [33mresource "aws_security_group" "insecure_sg" {
		[37m5  | [33m  name        = "allow_all"
		[37m6  | [33m  description = "Allow all inbound traffic"
		[37m7  | [33m  ingress {
		[37m8  | [33m    from_port   = 0
		[37m9  | [33m    to_port     = 0
		[37m10 | [33m    protocol    = "-1"
		[37m11 | [33m    cidr_blocks = ["0.0.0.0/0"]
		[37m12 | [33m  }
		[37m13 | [33m  egress {
		[37m14 | [33m    from_port   = 0
		[37m15 | [33m    to_port     = 0
		[37m16 | [33m    protocol    = "-1"
		[37m17 | [33m    cidr_blocks = ["0.0.0.0/0"]
		[37m18 | [33m  }
		[37m19 | [33m}

