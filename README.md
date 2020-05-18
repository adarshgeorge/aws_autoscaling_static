

Setting Autoscaling in aws account. 


First I going to create static auto scaling configuration


Quick Steps

1: Login to aws -> Ec2 Dashboard > Autoscaling.

2: First we need to Launch Configurations setup how ec2 need to spin up if during the ec2 downtime

3: Select AMI and add userdat

```
#!/bin/bash
yum install httpd -y
service httpd restart
chkconfig httpd on
echo "<h1><center> Hello World from Location 2A </center></h1>" > /var/www/html/index.html
```

4: Select the size of the root volume
5: Choose the security groups
6  Choose th key pair
7:  Launch th configuration file.

Now we need to create Autoscaling Group

1. Create auto caling group > Name the group, enter the number of the instance that you want to spin up.
2. Also add the all subnets
3. Choose the keep this group at its initials.
4.  Choose the name tag that you want identify the ec2 associated to this conf.
5: Okay

- Check in ec2 dashboard we can see the 3 ec2 spinned up.
- Try terminate one instance to check the autoscaling is working or not 
- Here you'll new ec2 instance will spinned up. 

