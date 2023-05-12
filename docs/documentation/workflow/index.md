---
icon: fontawesome/solid/arrows-spin
---

# :material-lock: Workflow

## AWS CloudFormation

!!! info "What is AWS CloudFormation?"
    Documentation available on [What is AWS CloudFormation? - AWS CloudFormation](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/Welcome.html).

    Opendesk is organised the following way:

    ```mermaid
    flowchart TD
        A[(Data Provider)]-->|File Upload|B[(AWS S3)]
        subgraph AWS [AWS]
        C[AWS Lambda]-.->|Trigger|B
        C-.->|Metadata|D[AWS DynamoDB]
        C-.->|Extract File|B
        end
        B-->|Online Access|E[Terminal]
    ```

AWS CloudFormation is a service that provides a model-based approach to provisioning and managing AWS resources. It allows you to create templates that define the resources you need, such as Amazon EC2 instances or Amazon RDS DB instances, and CloudFormation takes care of provisioning and configuring those resources automatically. 

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

This eliminates the need for manual resource creation and configuration, and also helps to manage the dependencies between resources. As a result, you can focus more on developing your applications that run on AWS, rather than spending time on resource management. The following scenarios illustrate how CloudFormation can be used to streamline the resource management process.

## :material-lock: Learn More...

Should you be interested in our approach and latest research on quantitative analysis, please feel free to contact us to obtain more detailed information about the PRO version of the package via **LinkedIn**.

[LinkedIn](https://www.linkedin.com/in/j-mr/ ){ .md-button .md-button--primary target="_blank" }