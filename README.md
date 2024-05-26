# Jenkins_Project_with_Docker-Agent


### Set up an AWS EC2 instance

1.
 Create an IAM user & login to your AWS Console
    - Access Type - Password
    - Permissions - Admin
2. Create an EC2 instance
    - Select an OS image - Ubuntu
    - Create a new key pair & download `.pem` file
    - Instance type - t2.micro
3. Connecting to the instance using ssh
```
ssh -i instance.pem ubunutu@<IP_ADDRESS>
```

### Installing Java

Pre-Requisites: Java (JDK)




1. Updating the outdated packages and dependencies
```
sudo apt update
```
2. Install java
```
sudo apt install openjdk-11-jre
```
3. Verify Java is Installed
```
java -version
```

### Install Jenkins

Now, you can proceed with installing Jenkins
Resources : jenkins.io (https://www.jenkins.io/doc/book/installing/linux/)
```
curl -fsSL https://pkg.jenkins.io/debian/jenkins.io-2023.key | sudo tee \
  /usr/share/keyrings/jenkins-keyring.asc > /dev/null
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update
sudo apt-get install jenkins
```

### A AWS EC2 instance was created🎉

![About Terraform](images/terraform.png)
