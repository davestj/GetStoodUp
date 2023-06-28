# GetStoodUp: ECR Base CloudFormation Setup Template

This CloudFormation template sets up an Elastic Container Registry (ECR) with the specified configuration.

## Parameters

The following parameters can be customized during stack creation:

- **RepositoryName**: Name of the ECR repository.
- **TagImmutability**: Specify whether to allow image tags to be overwritten. Default is set to `false`.
- **ScanOnPush**: Enable image vulnerability scanning on push. Default is set to `false`.
- **OtherAWSAccountId**: AWS Account ID for granting permissions to access the ECR repository.
- **OtherAWSUserName**: IAM User name in the other AWS account for granting permissions to access the ECR repository.
- **LifecyclePolicy**: ARN of the lifecycle policy to attach for maintenance.

## Resources

The CloudFormation template creates the following resources:

- **ECRRepository**: An ECR repository with the specified repository name, tag immutability, and image scanning configuration.
- **RepositoryPolicy**: Repository policy granting permissions to the specified AWS account and IAM user to access the ECR repository.
- **ECRRepositoryLifecyclePolicy**: Lifecycle policy attached to the ECR repository to automatically clean up old images every 120 days.

## Outputs

The CloudFormation stack provides the following outputs:

- **ECRRepositoryUrl**: URL of the ECR repository in the format `${AWS::AccountId}.dkr.ecr.${AWS::Region}.amazonaws.com/${RepositoryName}`.
- **ECRRepositoryName**: Name of the ECR repository.
- **ECRRepositoryLifecyclePolicyArn**: ARN of the lifecycle policy attached to the ECR repository.

## Usage

1. Launch the CloudFormation stack using this template, providing the required parameters.
2. Wait for the stack creation to complete.
3. Once the stack is created, you will have an ECR repository with the specified configuration.
4. Make note of the output values, such as the ECR repository URL, repository name, and lifecycle policy ARN, for future reference.

Note: Ensure that you have the necessary permissions to create resources in AWS CloudFormation and ECR, and that you replace the placeholders in the template with the appropriate values for your environment.

For more information on using CloudFormation, refer to the [AWS CloudFormation documentation](https://docs.aws.amazon.com/cloudformation).

## License

This project is licensed under the [GPL V3](LICENSE).

Feel free to customize and improve upon this CloudFormation template according to your requirements.

**Disclaimer**: Please review and understand the resources created by this CloudFormation template before deploying it in your environment. Use it at your own risk.
**Security**: Please note you will need to ensure proper Access controls are in place and edit these to fit the AWS Account.

