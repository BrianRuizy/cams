<h1 align="center">
    <img alt="CAMS_logo" title="CAMS" src="https://github.com/BrianRuizy/cams/blob/master/camslogo.png" width="160"> </br>
    E-TRaC
</h1>

Repository for the Demo and development version of E-TRaC.
The objective is for this repository to act as a platform template for future applications and reference.

![](https://camo.githubusercontent.com/d0f65430681b67b7104f6130ada8c098ec5f66ba/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f636f64652532307374796c652d7374616e646172642d627269676874677265656e2e7376673f7374796c653d666c6174)

## Dependencies

Frameworks and technologies include:

* [Flask](https://flask.palletsprojects.com/en/1.1.x/) microframework.
* [Docker](https://docs.docker.com/) containerization.
* AWS [EC2](https://docs.aws.amazon.com/ec2/index.html), and [ECR](https://docs.aws.amazon.com/ecr/index.html) cloud computing.

## Prerequisites

Must have the following accounts created, and security credentials at one's disposal:

- [x] AWS dev. account and credentials
- [x] AWS ECR access
- [x] Downloaded AWS Key Pairs
- [x] Docker Desktop installed
- [ ] Firebase privelages

Use the package manager [pip](https://pip.pypa.io/en/stable/) to install the following:

```bash
pip install flask
pip install docker-compose
pip install awscli
pip install ssh
```

```Python
import Flask==1.0.2
import Flask-Bootstrap4==4.0.2
import flask-navbar==1.0
import pycryptodome==3.7.3
import pyrebase==3.0.26
import pytz==2019.1
```

## Development Setup

### Remote into AWS Node using SSH

To connect to your local instance using SSH you specify the private key (.pem) file path, the user name for your AMI, and the public EC2 DNS name for your instance

`$ ssh -i '..\AWS keys\firstkey.pem' ec2-user@ec2-13-59-134-160.us-east-2.compute.amazonaws.com`

 you should then see the following warning message.

 `Warning: Permanently added 'ec2-198-51-100-1.compute-1.amazonaws.com' (RSA)
to the list of known hosts.`

### Setting up AWS and Docker

1. Launch Docker Desktop, if not done automatically at system boot.
2. Configure the AWS CLI with command line

```bash
$ aws configure
AWS Access Key ID [None]: AKIAIOSFODNN7EXAMPLE
AWS Secret Access Key [None]: wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY
Default region name [None]: us-east-2
Default output format [None]: json
```

3. Login into AWS ECR, and generate Docker login command
`aws ecr get-login --no-include-email`.
A login key command will be generated, paste it back to the command line. You should be prompted with a succesful login.

### Docker Commands

Action | Call
-----|--------------
Build | **docker-compose build**
Pull Container | **docker-compose pull**
Push Container | **docker-compose push**
Launch Package | **docker-compose up -d**
Check Logs | **docker-compose logs -tail 100 -f [ContainerName]**
Check Space | **docker system df**
Clear Space | **docker system prune -a**


© [Brian Ruiz](https://github.com/BrianRuizy)

------
