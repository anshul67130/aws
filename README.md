# AWS DevOps Website Deployment

## Step 1. Launch an Ubuntu EC2 instance

Signup to you aws console and under services select EC2 EC2\>Instances\>Launch an Instance 
![[1.png]]

| Configuration | Selection |
| - | - |
| **Instance Name** | `UbuntuEC2` |
| **OS Image** | `Ubuntu Server 26.04` |
| **Instance Type** | `t3.micro` |


Under network setting create a group named `customSecurityGroup`  
Allow Traffic of Port `80` for `http` and port `22` for `ssh`  Create and store private key for ssh authentication and then start the instance.

Here you will get a public ip for the EC2 instance. **Public IP** - `13.62.103.233`  use this to ssh into the instance.

## Step 2. SSH into server

Command - `ssh -i UbuntuEC2.pem ubuntu@13.62.103.233`
![[pictures/2.png]]

## Step 3. Update the system and then Install `nginx`

Command - `sudo apt update && sudo apt upgrade -y` This command is used to update the whole system To install `nginx` we use `sudo apt install nginx -y` After installing `nginx` it will start automatically 
![[pictures/3.png]]


## Step 4. Check the status of `nginx`

Command - `systemctl status ngnix` 
![[pictures/4.png]]


## Step 5. Check the  Webpage

Open you browser and go to the public ip address of EC2 instance . for us, it is `http://13.62.103.233` If we don't specify any port, by default it will go to port 80 where our `nginx` server is hosted 
![[pictures/5.png]]

Here we can see that we have successfully created an EC2 instance and deployed an `nginx` server on it.

