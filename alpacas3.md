Exercise to learn the Basisc about AWS S3, CLI and Github actions

1. Upload static Website via Console

1. Start your Sandbox
1. Create a new S3 Bucket
1. Drag and drop the index.html
1. Make the file public available
1. Enable website hosting
1. Place your alpaca

# start you sandbox
open repository in github friday's task
+ copy ssh key from code
`cd`
`cd Desktop`
`git clone SSH key`

clone html file into your computer using visualstudio or terminal
open sandbox - startlab- click aws
# create bucket
 click create bucket, give name with small letters, then click AC enabled and uncheck bucket policies to public
 create bucket
 # or
 click create bucket, give name then, create a bucket
# Drag and drop the index.html
 drop and drag html file
  # Permission access control list
    + If AL is not enabled during bucket creation. In permission, click on bucket owner enforced to enble it and then click on edit ACL, Check read to everyone and check ackknowledge it.
    + Enable ACL
    + Edit acl give permission click on ACL everyone read and save change

## or

# Enable website hosting
In properties- enable ststic web hosting
enter or include index.html
# bucket policy
 add bucket policy
 [code]({
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "PublicReadGetObject",
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:GetObject",
            "Resource": "arn:aws:s3:::frinew1bucket/*"
        }
    ]
})
[link](https://docs.aws.amazon.com/AmazonS3/latest/userguide/WebsiteAccessPermissionsReqd.html#block-public-access-static-site)

# Place your alpaca
 + Click on the html [link](http://frinew1bucket.s3-website-us-west-2.amazonaws.com) in properties
 + opens new page with alpaca then click on image it will work


2. Upload static Website via cli

1. Install the aws CLI
1. Start your Sandbox
1. Configure CLI
1. Create a new S3 Bucket
1. Upload index.html
1. Make the file public available
1. Enable website hosting
1. Place your alpaca (click in the browser ;))

## Install the aws CLI
  `brew install awscli`
## Start your Sandbox
 + After installing AWSCLI 
   * `cd`

## Configure CLI
   * `aws configure`
  + enter access key and secret access key as none
  + enter region as `eu-central-1`
  + enter format as `json`
    * `cd .aws`
    * `rm credentials`
    #copy AWS CLI from sandbox- AWS details and paste it in the "crendential- .aws file"
    * To find .aws file
    `cmd+shift+.`
    * `vim credential or touch credentials`
    `:wq`
## Create a new S3 Bucket
   `aws s3api create-bucket --bucket s3cpibucket --region us-east-1 `
## Upload index.html
`aws s3 cp Documents/26.sep.2022/Friday_challenge/cgn-aws-22-3-friday-challanges/22-09-30_S3-CLI-Actions/index.html s3://s3cpibucket`

## Make the file public available
`aws s3api put-object-acl --bucket s3cpibucket --key index.html --acl public-read`
## or
`aws s3 cp Documents/26.sep.2022/Friday_challenge/cgn-aws-22-3-friday-challanges/22-09-30_S3-CLI-Actions/index.html s3://s3cpibucket --acl public-read`
[ref](https://aws.amazon.com/premiumsupport/knowledge-center/read-access-objects-s3-bucket/)

## Enable website hosting
`aws s3 website s3://s3cpibucket/ --index-document index.html`
## [links](https://docs.aws.amazon.com/cli/latest/reference/s3/website.html)
## [Link](https://sammeechward.com/aws-cli-s3-static-website/)
## [reference](https://docs.aws.amazon.com/cli/latest/index.html)
## [ref2](https://gcore.com/support/articles/360002115857/)


Place your alpaca (click in the browser ;))


