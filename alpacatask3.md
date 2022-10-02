3. Upload static Website via github actions (Optional)

1. Create a new github repository
1. Add the index.html to the repsoitory
1. Change the title of the page with a Pull Reqeuest
1. Add a github Action that creates and deploy the index.html to the sandbox via cli (Use Secrets to setup the cli credentials)
1. Place your alpaca (click in the browser ;))

# Before Creating Repository
`cd Desktop`
`mkdir apaca_aws`
- copy html file to apaca_aws
`cd apaca_aws`
`git init`
`git status`
`git add index.html`
`git commit -m "First commit"`

# Create a new github repository
## Create new repository using GITHUB
copy remote repo code and paste it in the Terminal
`git remote add origin git@github.com:Shaktam/apacafile_html.git
git branch -M main
git push -u origin main
`

## Create a new S3 Bucket
   `aws s3api create-bucket --bucket s3cpibucket.github --region us-east-1 `
## Upload index.html
`aws s3 cp Documents/26.sep.2022/Friday_challenge/cgn-aws-22-3-friday-challanges/22-09-30_S3-CLI-Actions/index.html s3://s3cpibucket.github`   

## Make the file public available
`aws s3api put-object-acl --bucket s3cpibucket.github --key index.html --acl public-read`   
## Enable static website 
`aws s3 website s3://s3cpibucket.github/ --index-document index.html`

## create a Branch
`git branch subaws`
`git switch subaws`
## To edit a file in Terminal
`vim index.html`

edited click a place alpaca as click a place `Awesome` alpaca
 to return to git
`:qal`
`:wq`
`git add index.html`
`git commit -m "modified text in HTML file"`
# Add the index.html to the repsoitory

## To push this file into repository
`git push`
- it gives a new command copy and paste it
`git push --set-upstream origin subaws`

# Change the title of the page with a Pull Reqeuest
- once the git push is done,in a github page it'll show a message to compare and pull request while we're still in branch not in main.
- once click on compare and pull request-create pull request.
-file changed- shows the changes made then compare and give the review.
- merge pull request.
- can delete branch remotely
- check html file.
## In Terminal
`git switch main`
`git pull`
`git status`
`git branch -D subaws`
`git branch`

# Add a github Action that creates and deploy the index.html to the sandbox via cli (Use Secrets to setup the cli credentials)

`Action - create new workflow - Edit name- edit file `
- [Mydeploy](Edited_deploy_file.md/My_edited_file.md)
- [Fabdeploy](Edited_deploy_file.md/Fab_deployfile.md)

* Open html file and edit color, time (0.5,0.2) and name as we like
* save changes
* check status, leave if all green

## to add seceret key
settings- secret- Action- add secret key-`AWS_ACCESS_KEY_ID`-`Access kex from aws details AWS CLI` ans aws secert accesskey and secret token


# Place your alpaca (click in the browser ;))

Check link in AWS console s3 bucket alpaca would move faster and name would've changed