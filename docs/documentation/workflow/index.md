---
icon: fontawesome/solid/database
---

# Workflow

!!! info "What is AWS CloudFormation?"
    Documentation available on [What is AWS CloudFormation? - AWS CloudFormation](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/Welcome.html)


```mermaid
sequenceDiagram
    Data Provider->>AWS S3: File Upload
    AWS S3-->>AWS Lambda: Trigger Lambda Function
    AWS Lambda-->>AWS DynamoDB: Metadata Store
    AWS Lambda-->>AWS S3: Extract File Uploaded
    AWS S3-->>AWS Lambda: Trigger Lambda Function
    AWS Lambda-->>AWS S3: HTML Upload
    AWS S3->>Terminal: Online Access
```

AWS CloudFormation is a service that provides a model-based approach to provisioning and managing AWS resources. It allows you to create templates that define the resources you need, such as Amazon EC2 instances or Amazon RDS DB instances, and CloudFormation takes care of provisioning and configuring those resources automatically. This eliminates the need for manual resource creation and configuration, and also helps to manage the dependencies between resources. As a result, you can focus more on developing your applications that run on AWS, rather than spending time on resource management. The following scenarios illustrate how CloudFormation can be used to streamline the resource management process.