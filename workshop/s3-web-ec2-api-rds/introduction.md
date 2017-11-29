# Introduction

We are ready to start the deployment of our website.
The first step will be the frontend. Because it’s a static website, we can create an [S3 bucket](http://docs.aws.amazon.com/AmazonS3/latest/dev/UsingBucket.html), put all the code in it and serve it as a static website. Think of an S3 bucket as a folder on the cloud.
To automate the build we will use [CodeBuild](https://aws.amazon.com/codebuild/), AWS option to build projects on the go.
CodeBuild will pull our repository, build the webpage and copy the build directory to S3. The configuration is specified on `buildspec.frontend.yml` on the root folder of our repo.

In this section we will also create our Postgres database in [AWS RDS](http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Welcome.html).

Finally we will use [CodeDeploy](http://docs.aws.amazon.com/codedeploy/latest/userguide/welcome.html) to automate the deployment of our API to the EC2 instances. It will pull the repo from our EC2 instances and start gunicorn. You should take a look at the configuration files located in `infrastructure/aws/codedeploy`.

---

**Next:** [Serve a static website from S3](/workshop/s3-web-ec2-api-rds/01-serve-website-from-s3.md)