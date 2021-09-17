This demo use Codepipeline to update an EKS cluster!
Good referencing: https://itnext.io/continuous-deployment-to-kubernetes-eks-using-aws-codepipeline-aws-codecommit-and-aws-codebuild-fce7d6c18e83

Remarks
(1) To allow build docker image by CodeBuild, enable "Privilaged" is required in the Environment setup <br>
![image](https://user-images.githubusercontent.com/33850004/133379569-9e74c85b-34cc-4452-9133-dda326934f6d.png) <br><br>

(2) To allow CodeBuild to push docker image to ECR, CodeBuild role requires policies as follow: <br>
![image](https://user-images.githubusercontent.com/33850004/133787414-3ea36049-037d-49f0-b916-5639b6527aa9.png) <br><br>

(3) Build env reference setup (co-relate with buildspec.yaml) <br>
![image](https://user-images.githubusercontent.com/33850004/133384357-f3e2ad8d-b100-4802-9966-d5c60da3350d.png) <br>
also includes $TAG:latest<br><br>
