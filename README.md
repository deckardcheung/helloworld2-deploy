This demo use Codepipeline to update an EKS cluster!
Good referencing: https://itnext.io/continuous-deployment-to-kubernetes-eks-using-aws-codepipeline-aws-codecommit-and-aws-codebuild-fce7d6c18e83

Remarks
(1) To allow build docker image by CodeBuild, enable "Privilaged" is required in the Environment setup
![image](https://user-images.githubusercontent.com/33850004/133379569-9e74c85b-34cc-4452-9133-dda326934f6d.png)

(2) Build env reference setup (co-relate with buildspec.yaml)
![image](https://user-images.githubusercontent.com/33850004/133384357-f3e2ad8d-b100-4802-9966-d5c60da3350d.png)

(3) Dev > CodeBuild Role > +policy: AmazonEC2ContainerRegistryPowerUser <br>
(4) Deploy > CodeBuild Role > +New inline policy: Name: EKSClusterAccess <br>
    {
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "VisualEditor0",
            "Effect": "Allow",
            "Action": "eks:DescribeCluster",
            "Resource": "*"
        }
    ]
}
