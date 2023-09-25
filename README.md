# Deployment of a Highly Scalable and Available Web Applications on AWS

![website drawio](https://github.com/pradip2994/AWS_project_Highly_Available_Web_Applications/assets/124191442/f6e890a9-87b9-49f7-8e71-a475ff2bc6db)

## Step-by-Step Guide to Deploy web Application

## Create VPC (Virtual Private Cloud)

![Screenshot 2023-09-25 114439](https://github.com/pradip2994/web/assets/124191442/24747961-fee1-45b4-8071-c646394fd960)


## Create IGW and attach to VPC

![Screenshot 2023-09-25 114553](https://github.com/pradip2994/web/assets/124191442/c28a5954-426b-4151-9c19-491c22033e1f)

![Screenshot 2023-09-25 114655](https://github.com/pradip2994/web/assets/124191442/878198d7-fec3-44b2-bc29-842fa58ae769)


## Create Subnets
1) create public subnet in both the AZs.
2) create private subnet for webserver and database in both the AZs.

![Screenshot 2023-09-25 115405](https://github.com/pradip2994/web/assets/124191442/3197b645-597e-4183-adfe-29ec576c3651)

## Create Route Table.

create route table and accociate subnet and give internet route to public subnet.

![Screenshot 2023-09-25 120132](https://github.com/pradip2994/web/assets/124191442/72120256-f330-4eff-960e-d081c0346098)

## Create Security Group

![Screenshot 2023-09-25 121539](https://github.com/pradip2994/web/assets/124191442/764aac54-03c3-4b86-ba13-303a57e29135)


## Create NAT Gateway
![Screenshot 2023-09-25 121941](https://github.com/pradip2994/web/assets/124191442/527a8057-ed4a-4ab3-b8ff-8badfee15c7d)

### Subnet association with Public Subnets

![Screenshot 2023-09-25 122308](https://github.com/pradip2994/web/assets/124191442/99aa55f7-6ff9-455e-9749-70e5a1f0a9f7)

## Create Keypair

![Screenshot 2023-09-25 122600](https://github.com/pradip2994/web/assets/124191442/98b87164-bf29-414d-81b4-8b73fa710e52)


## Now real things starts from here. 

## Create Subnet group in RDS 

![Screenshot 2023-09-25 122844](https://github.com/pradip2994/web/assets/124191442/2b788fa8-28f3-4e26-a0e5-503e951d580e)

### Subnet has been created

![Screenshot 2023-09-25 122900](https://github.com/pradip2994/web/assets/124191442/a5f27d5d-19d1-493f-bd17-d6af9f5cb764)

## Create RDS and select MySql

![Screenshot 2023-09-25 122919](https://github.com/pradip2994/web/assets/124191442/7e434bdb-394f-4c18-bbae-196ed6031580)

![Screenshot 2023-09-25 122930](https://github.com/pradip2994/web/assets/124191442/1e50fb4a-09bc-41d1-ab36-b1e7f1e1ee6a)

![Screenshot 2023-09-25 122942](https://github.com/pradip2994/web/assets/124191442/5a6d3d14-1609-4034-bc2e-6c736f8ba6ba)

![Screenshot 2023-09-25 123053](https://github.com/pradip2994/web/assets/124191442/30e06475-88de-40d1-8828-8e57a5421717)

![Screenshot 2023-09-25 123140](https://github.com/pradip2994/web/assets/124191442/29a5e8b6-ecf1-4818-a5bb-8395f0237f4b)

![Screenshot 2023-09-25 123206](https://github.com/pradip2994/web/assets/124191442/33dc3c24-dd2e-4530-9bd3-453af1fafbe4)

![Screenshot 2023-09-25 123219](https://github.com/pradip2994/web/assets/124191442/fb6c53c5-388f-4027-ab32-a20dac8c1a8e)

### RDS database has been created

![Screenshot 2023-09-25 123552](https://github.com/pradip2994/web/assets/124191442/e27b94c6-3390-4c63-9b70-17e85d1ee8bf)

## For Standby RDS click on Action then click on MultiAZ

![Screenshot 2023-09-25 124258](https://github.com/pradip2994/web/assets/124191442/726c3ede-5f82-4cfe-922f-d25333c6e1ae)

### click on apply immediately then click on convert to MultiAZ.

![Screenshot 2023-09-25 124313](https://github.com/pradip2994/web/assets/124191442/b432426b-e93d-48df-bbdd-18c87a4374a5)

### Multi-AZ DB instance deployment done.

![Screenshot 2023-09-25 125905](https://github.com/pradip2994/web/assets/124191442/9f1673c1-2447-4749-8b52-852cacfc432c)

## Create EFS (Elastic File System)

![Screenshot 2023-09-25 130139](https://github.com/pradip2994/web/assets/124191442/9aead137-7c31-47d3-8348-f6a2f63713a9)

![Screenshot 2023-09-25 130230](https://github.com/pradip2994/web/assets/124191442/af802ecb-3adf-467f-bbe3-f6059c9a8e23)

![Screenshot 2023-09-25 130244](https://github.com/pradip2994/web/assets/124191442/06c41139-bf90-4b93-be76-cce40cabb299)

![Screenshot 2023-09-25 130322](https://github.com/pradip2994/web/assets/124191442/404d1e66-7350-46db-944a-9990f07f7f42)

![Screenshot 2023-09-25 130341](https://github.com/pradip2994/web/assets/124191442/f3749994-42bc-4fa4-9781-0261d25b09d6)

Now you can see that EFS File System has been created.

![Screenshot 2023-09-25 130357](https://github.com/pradip2994/web/assets/124191442/41fb8e72-f11e-435a-8069-5b6001d74723)

## Now launch ubuntu EC2 and install all software needed and dependencies required and also configure RDS and mount EFS. Below are the steps which have to perform on EC2 and Create AMI. 

![Screenshot 2023-09-25 131149](https://github.com/pradip2994/web/assets/124191442/84ef27f7-4e06-41e7-a583-7ceb2b53b2e0)


## Install MySql Client.

```
apt-get update

apt-get install mysql-client -y
````

![Screenshot 2023-09-25 131800](https://github.com/pradip2994/web/assets/124191442/c190855f-a98a-43b4-bcbb-cac4c5b1bb97)


## Install apache webserver.

```
apt-get install apache2 -y

systemctl status apache2
```

## Install PHP and related packages 

```
apt-get install php libapache2-mod-php php-mysql -y
```

## Install NFS client

```
sudo apt-get update
```

### Install git and binutils, using the following command. binutils is required for building DEB packages,

```
sudo apt-get -y install git binutils
```

### Clone amazon-efs-utils from GitHub using the following command.

```
git clone https://github.com/aws/efs-utils
```

### Navigate to the directory that contains the amazon-efs-utils package.

```
cd efs-utils
```

### Build amazon-efs-utils using the following command:

```
./build-deb.sh
```

### Install the package with the following command.

```
sudo apt-get -y install ./build/amazon-efs-utils*deb
```

### Run the following commands to install wget.

```
sudo apt-get update
sudo apt-get -y install wget
```

### Use the following script to install the appropriate version of the pip package manager.

```
if echo $(python3 -V 2>&1) | grep -e "Python 3.6"; then
    sudo wget https://bootstrap.pypa.io/pip/3.6/get-pip.py -O /tmp/get-pip.py
elif echo $(python3 -V 2>&1) | grep -e "Python 3.5"; then
    sudo wget https://bootstrap.pypa.io/pip/3.5/get-pip.py -O /tmp/get-pip.py
elif echo $(python3 -V 2>&1) | grep -e "Python 3.4"; then
    sudo wget https://bootstrap.pypa.io/pip/3.4/get-pip.py -O /tmp/get-pip.py
else
    sudo apt-get -y install python3-distutils
    sudo wget https://bootstrap.pypa.io/get-pip.py -O /tmp/get-pip.py
fi
```

### Run the following commands to install botocore.

```
sudo python3 /tmp/get-pip.py
sudo pip3 install botocore
```

### Mount EFS to the destinationusing mount via IP.

![Screenshot 2023-09-25 132511](https://github.com/pradip2994/web/assets/124191442/b16cdf42-5f9a-4c3c-a0c7-6b4346d46488)

### click on attach.

![Screenshot 2023-09-25 132616](https://github.com/pradip2994/web/assets/124191442/e5a74053-4a8e-4606-8017-0a1245cae7f1)

### Copy command and paste on command prompt.

```
sudo mount -t nfs4 -o nfsvers=4.1,rsize=1048576,wsize=1048576,hard,timeo=600,retrans=2,noresvport 10.0.2.132:/ /var/www/html

df -h
```

![Screenshot 2023-09-25 132811](https://github.com/pradip2994/web/assets/124191442/12e909c9-f1b6-49b6-8dbf-59a53865c58a)

### Go to /etc/fstab and update endpoint of EFS

![Screenshot 2023-09-25 132901](https://github.com/pradip2994/web/assets/124191442/6b9998b8-8f6f-4a05-b981-a31abd02831f)

![Screenshot 2023-09-25 133036](https://github.com/pradip2994/web/assets/124191442/fd670569-948e-447b-8c59-0810f0d25e6e)

```
nano /etc/fstab
10.0.2.169:/ /var/www/html nfs4 defaults 0 0
```

## Reboot system and check mounted efs is showing or not.
```
df -h
```

![Screenshot 2023-09-25 133914](https://github.com/pradip2994/web/assets/124191442/8153450b-3324-4c39-a2d3-a28660e6eb72)

## Connect Rds with mysql client

```
mysql -h <database-endpoint> -u <user-name> -p
```

![Screenshot 2023-09-25 134227](https://github.com/pradip2994/web/assets/124191442/e355b977-5203-47ab-8916-4c437a98b5c7)

### Create Database

```
CREATE DATABASE wordpress;
CREATE USER 'wordpress' IDENTIFIED BY 'wordpress-pass';
GRANT ALL PRIVILEGES ON wordpress.* TO wordpress;
FLUSH PRIVILEGES;
Exit
```

![Screenshot 2023-09-25 134349](https://github.com/pradip2994/web/assets/124191442/8c467136-8350-403b-805f-e4f8bd43d280)

## Download the latest WordPress File

```
wget https://wordpress.org/latest.tar.gz
```

### Uncompress the tarball which will generate a folder called “wordpress” 

```
tar -xvf latest.tar.gz

ls
cd wordpress/
ls
cp wp-config-sample.php wp-config.php
```

### Now Enter database name, username, password, host and configure Authentication Unique Keys and Salts.

```
nano wp-config.php
```

![Screenshot 2023-09-25 134714](https://github.com/pradip2994/web/assets/124191442/52f62f7d-6086-4811-82f5-18e43164de6a)

Goto this website and copy and paste here. https://api.wordpress.org/secret-key/1.1/salt/

![Screenshot 2023-09-25 134852](https://github.com/pradip2994/web/assets/124191442/9a4e0dcd-0106-4b76-b30a-b94b7e704f7f)

```
cd ..
ls
```

### Copy wordpress content to destination.

```
sudo cp -r wordpress/* /var/www/html/
```

### Restart apache webserver.

```
systemctl restart apache2
```

## Now Stop the Instance and Create AMI 
### In below image you can see that AMI is created.

![Screenshot 2023-09-25 140323](https://github.com/pradip2994/web/assets/124191442/bffe7ce4-489f-49c7-aa01-1cd7849aad4b)

## Create Load Balancer

![Screenshot 2023-09-25 140915](https://github.com/pradip2994/web/assets/124191442/c7df2001-7e7e-42a6-8d86-4c70ab581c9d)

## Create Application Load Balancer (ALB)

![Screenshot 2023-09-25 174159](https://github.com/pradip2994/web/assets/124191442/3df82ea1-57d6-4a59-afa3-49507ecc9fa8)

![Screenshot 2023-09-25 174258](https://github.com/pradip2994/web/assets/124191442/f87d695f-9f94-4654-b0c4-7044357b792e)

![Screenshot 2023-09-25 174323](https://github.com/pradip2994/web/assets/124191442/d58147a4-002d-4374-b508-b2f54124b442)

![Screenshot 2023-09-25 174403](https://github.com/pradip2994/web/assets/124191442/e9bf7418-73f0-40b7-81a7-d4bc50fed18b)

## Create Target Groups

![Screenshot 2023-09-25 174413](https://github.com/pradip2994/web/assets/124191442/e7383f12-affe-432f-bd53-db53454928c5)

![Screenshot 2023-09-25 174437](https://github.com/pradip2994/web/assets/124191442/824e089a-fe36-49e1-b464-4bae39d5d2ca)

![Screenshot 2023-09-25 174502](https://github.com/pradip2994/web/assets/124191442/62bacea5-5429-43e8-9b02-09286b91a3fa)

### target group created
![Screenshot 2023-09-25 174512](https://github.com/pradip2994/web/assets/124191442/1d21ce76-230f-4f35-aedf-e8a8ad4c6880)

### now refresh and select target group

![Screenshot 2023-09-25 174533](https://github.com/pradip2994/web/assets/124191442/1730b9c0-298b-4f43-bf1d-8221a047404c)

### Application Loadbalancer created

![Screenshot 2023-09-25 175039](https://github.com/pradip2994/web/assets/124191442/440e6a6d-61e0-4cc0-8dbd-f826e5695786)


## Create Auto Scaling Group

![Screenshot 2023-09-25 175334](https://github.com/pradip2994/web/assets/124191442/6ae9961d-01cd-4633-8b94-5968291e80aa)

### Create Launch Templates

![Screenshot 2023-09-25 144233](https://github.com/pradip2994/web/assets/124191442/5e6a495b-1ef0-4130-9079-d0f7dd2c4314)

![Screenshot 2023-09-25 144312](https://github.com/pradip2994/web/assets/124191442/8ab59dd0-33d4-4ce2-bdaa-f425032c1f64)

![Screenshot 2023-09-25 144325](https://github.com/pradip2994/web/assets/124191442/d8358309-a9f0-4657-b1cd-c63d5db0550d)

![Screenshot 2023-09-25 144409](https://github.com/pradip2994/web/assets/124191442/007cf53a-b7b2-4159-8117-c7b40fc198ce)

![Screenshot 2023-09-25 144430](https://github.com/pradip2994/web/assets/124191442/5d5f6abf-8307-4403-bb33-c78883b8228b)

### Refresh Launch Template

![Screenshot 2023-09-25 175918](https://github.com/pradip2994/web/assets/124191442/757a1065-4d86-497b-b8f0-601f2444e7b9)

![Screenshot 2023-09-25 175943](https://github.com/pradip2994/web/assets/124191442/36cffba6-6469-420e-b6d9-328d2ad88653)

![Screenshot 2023-09-25 175956](https://github.com/pradip2994/web/assets/124191442/ec6ed652-428c-4839-b0fd-3f1fa634d870)

![Screenshot 2023-09-25 180040](https://github.com/pradip2994/web/assets/124191442/287bb5c2-c2ee-43b7-bcd8-0c558aad0b33)

![Screenshot 2023-09-25 180046](https://github.com/pradip2994/web/assets/124191442/c2581921-d88e-4ce2-9938-5724575f9219)

## Auto Scaling Group has been created

![Screenshot 2023-09-25 180106](https://github.com/pradip2994/web/assets/124191442/3fc3c9e7-fb6e-4fb4-9629-3243e94eac35)

### Now you can see that Autoscaling group has created instances.

![Screenshot 2023-09-25 180432](https://github.com/pradip2994/web/assets/124191442/d6230dae-53da-4173-9a61-d5ab38df2d2d)

## Register a New Domain Name in Route 53

![Screenshot 2023-09-25 145458](https://github.com/pradip2994/web/assets/124191442/f847edca-9d22-464c-bd26-5df3b2881081)

## On Route53 click on Hosted Zone, Create a Record Set in Route 53

![Screenshot 2023-09-25 145614](https://github.com/pradip2994/web/assets/124191442/f8262c48-1660-4207-833e-e96e5af16db9)

### Create 2 record, In Record Name enter www, enable Alias, Click on Route traffic to Alias to application and classic load balancer, select region then select from the dropdown loadbalancer.

![Screenshot 2023-09-25 180816](https://github.com/pradip2994/web/assets/124191442/18963ed3-2b18-49cf-b4b0-ef0f9aa43453)

### You can see that Record has been created for www and the main domain.

![Screenshot 2023-09-25 180924](https://github.com/pradip2994/web/assets/124191442/66e973a8-e7cd-4c7c-badc-b9fda07bbf61)

## Now entering the Domain name in Browser, you can see wordpress website

![Screenshot 2023-09-25 181309](https://github.com/pradip2994/AWS_project_Highly_Available_Web_Applications./assets/124191442/19be2ff2-67eb-4344-a82d-37aaf1d83463)

## Enter your details and login.

![Screenshot 2023-09-25 181429](https://github.com/pradip2994/AWS_project_Highly_Available_Web_Applications./assets/124191442/a167a7d5-0252-4b74-a634-923ee91a4ab7)
![Screenshot 2023-09-25 181441](https://github.com/pradip2994/AWS_project_Highly_Available_Web_Applications./assets/124191442/a273e3ef-3a93-4c96-8419-f18a07edddc8)

### Now you can see welcome to WordPress by entering Domain name. 

![Screenshot 2023-09-25 181650](https://github.com/pradip2994/AWS_project_Highly_Available_Web_Applications./assets/124191442/5fedaebc-f394-4f4c-891a-d9fc5c323782)

## Register SSL Certificate in AWS Certificate Manager for secure connection. 

![Screenshot 2023-09-25 190105](https://github.com/pradip2994/AWS_project_Highly_Available_Web_Applications./assets/124191442/b848df3d-dc5c-44d1-a25a-00bfcc3dd66f)

![Screenshot 2023-09-25 190111](https://github.com/pradip2994/AWS_project_Highly_Available_Web_Applications./assets/124191442/ec2d17ba-0b81-44f6-88b0-f7f01e22ea2a)

![Screenshot 2023-09-25 190210](https://github.com/pradip2994/AWS_project_Highly_Available_Web_Applications./assets/124191442/2d6310a3-0790-439c-b304-e38a757391ad)

![Screenshot 2023-09-25 190310](https://github.com/pradip2994/AWS_project_Highly_Available_Web_Applications./assets/124191442/136836ab-7a41-4fe5-bbce-66d7942e064d)

## Now go to Loadbalancer and Add Listener

![Screenshot 2023-09-25 190430](https://github.com/pradip2994/AWS_project_Highly_Available_Web_Applications./assets/124191442/0f4f27a5-0141-4d42-aadb-ed7e6c32ff79)

![Screenshot 2023-09-25 190453](https://github.com/pradip2994/AWS_project_Highly_Available_Web_Applications./assets/124191442/4d13b153-c3d2-4389-91b8-c804d2abd463)

![Screenshot 2023-09-25 190503](https://github.com/pradip2994/AWS_project_Highly_Available_Web_Applications./assets/124191442/8d62909b-879f-4040-b5f3-36ce53751d0c)

![Screenshot 2023-09-25 190527](https://github.com/pradip2994/AWS_project_Highly_Available_Web_Applications./assets/124191442/38c317eb-732f-46b7-98c8-7aba06d3640e)

### Also Edit Http:80 Rule

![Screenshot 2023-09-25 190931](https://github.com/pradip2994/AWS_project_Highly_Available_Web_Applications./assets/124191442/1315be8a-c1a7-4f6e-ac87-21aa4e064658)

![Screenshot 2023-09-25 191051](https://github.com/pradip2994/AWS_project_Highly_Available_Web_Applications./assets/124191442/f9973090-605a-4ff4-940e-c6be2c501020)

# Now access domain name in browser, you can see it is securely connected with https  

![Screenshot 2023-09-25 191709](https://github.com/pradip2994/AWS_project_Highly_Available_Web_Applications./assets/124191442/4f68daf4-69c7-4e51-a215-3f836f64fb27)




## Thank you! 
