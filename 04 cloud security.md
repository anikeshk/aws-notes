- AWS Shared Responsibility Model
	- AWS: Responsibility for security “of” the cloud
	- Customers: Responsibility for security “in” the cloud
- Difference in control in IaaS (EC2) vs PaaS (Lambda) vs SaaS  (Trusted Advisor or Chime)
- AWS Identity and Access Management (IAM)
	- No-cost/free to use
	- Global service
	- Manage access to AWS resources; fine-grained access rights (who, which, how)
- Components
	- IAM user
	- IAM group
	- IAM policy
	- IAM role
- Authentication as an IAM user
	- Programmatic access
	- AWS Management Console access
- IAM Multi-Factor Authentication (MFA)
- Authorization: all permissions are implicitly denied by default; assign permission using IAM policy 
- Best practice: follow the principle of least privilege
- IAM policies
	- Identity-based policies: attached to an user
	- Resource-based policies: attached to a resource
	- Written in JSON
	- “deny statement always wins”
- IAM groups
	- Collection of IAM users (like Admin)
	- Cannot be nested, contains only users
- IAM roles
	- Similar to IAM user
	- Intended to be assumable by a person, application, or service
	- Ex: an EC2 instance needs read-only access to an AWS S3 bucket, role is assumed by EC2 instance
	- Categories: AWS service, Another AWS account, Web identity (Cognito or any OpenID provider), SAML 2.0 federation
- AWS root user/AWS root account
	- Do not use for daily work
	- Use AWS CloudTrail: tracks user activity on your account; 90 days history available by default
	- Change the AWS Support Plan
- Encryption at rest (AWS KMS for encryption keys) vs encryption in transit (AWS Certificate Manager for TLS certificates)
- Tools and options for controlling access to Amazon S3 data
	- Amazon S3 Block Public Access
	- IAM policies
	- Bucket policies
	- Access control lists (ACLs)
	- AWS Trusted Advisor bucket permissions check
- Compliance programs
	- Certifications and attestations
	- Laws, regulations, and privacy
	- Alignments and frameworks
- AWS Config: access, audit, and evaluate the configurations of AWS resources
- AWS Artifact: is a resource for compliance-related information (can access AWS ISO certifications)

IAM Policy
```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": [
                "s3:Get*",
                "s3:List*",
                "s3:Describe*",
                "s3-object-lambda:Get*",
                "s3-object-lambda:List*"
            ],
            "Resource": "*"
        }
    ]
}
```
- **Effect** says whether to _Allow_ or _Deny_ the permissions.
- **Action** specifies the API calls that can be made against an AWS Service (eg _cloudwatch:ListMetrics_).
- **Resource** defines the scope of entities covered by the policy rule (eg a specific Amazon S3 bucket or Amazon EC2 instance, or * which means _any resource_).
