# AWS VPC production
![alter text](images/p2.png)<br>
1.Access the EC2 Dashboard:<br>
Log in to the AWS Management Console.<br>
Navigate to Services > EC2.<br>
In the left-hand menu, select Load Balancers under the Load Balancing section.<br>
Create a Load Balancer:
## step 2 : create a load balancer
Click on the Create Load Balancer button.<br>
Choose Application Load Balancer (ALB) for HTTP/HTTPS traffic distribution.<br>
Configure the Load Balancer Settings:<br>

Provide a name for your Load Balancer in the Name field.
Set the Scheme to Internet-facing to allow external traffic.
Choose IP Address Type as IPv4.
Under Network mapping, select the VPC you created earlier.
Enable Availability Zones:

Activate at least 2 Availability Zones for high availability.
Select Public Subnets for each Availability Zone where your instances are deployed.
Configure the Security Group:

Assign a Security Group that allows traffic to your Load Balancer.
For example, ensure the following rules are added to the Security Group:
HTTP (TCP, Port 80, Source: Anywhere).
HTTPS (TCP, Port 443, Source: Anywhere), if using SSL.
Security Settings (Optional):

If you're using HTTPS, configure the SSL Certificate here. Otherwise, skip this step.
Configure Routing Settings:

Under Routing, create a new Target Group by clicking Create a new target group.
Create a Target Group:

Enter a name for your Target Group.
Set the Target Type to Instances to distribute traffic among EC2 instances.
Select the VPC where your instances are deployed.
Configure Health Check Settings:
Protocol: Choose HTTP or HTTPS.
Path: Specify the health check path (e.g., /index.html).


