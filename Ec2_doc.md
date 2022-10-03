# Terminal

1. create a file with vim
1. delete a file
1. move to the downloads folder
1. move to user home directory

# S3

## Do with console and cli:

1. create a s3 bucket
1. upload a file
1. delete a file
1. upload a public file

# EC2

1. start an ec2 Instance
1. login to an ec2 Instance via ssh
1. set the role of an ec2 instance
1. Download a file from s3 to ec2
1. create a file with vim on the ec2 instance and upload it to s3

# EC2

### Task 1

## start an ec2 Instance
open AWS console- EC2 Instance- launch instance-`- name
                                                 - amazon linux
                                                 - instance type
                                                 -select or create key pair
                                                 - launch instance`

open instance- connect

open sandbox- aws details- Download pem.

open VS code or terminal

`cd`

`cd Downloads`

copy chmod from EC2 instance connect and ssh key, then use it in terminal

`chmod 400 labsuser.pem`

`ssh -i "labsuser.pem" ec2-user@ec2-34-212-225-33.us-west-2.compute.amazonaws.com`
`yes`
now connected to aws linux.
`whoami`

`hostname -s`

`uptime -p`

`who -H -a`

`TZ=America/New_york date`

`cal -j`

`cal -s`

`cal -m`

### Task 2

[Link](https://labs.vocareum.com/main/main.php?m=clabide&mode=s&asnid=1114192&stepid=1114193&hideNavBar=1)
 follow steps to create
 