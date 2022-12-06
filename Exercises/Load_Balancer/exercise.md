## Problem Statement 

### How to create a Simple Application Load Balancer on AWS

### Pre-requisites: -
1) Create 2 different instances where 2 different websites hosted on that machines as shown in the image.</br>
For Reference =[How to Host static Website on EC2](../Static_Website_EC2/solution_static_website_EC2.md)
2) Create a Security Group (where inbound & outbound rules specify as per the needs)
3) Create a Target Group (where 2 instances allocated as per the requirement)

### Steps:-
1) After Done With Pre-requisites Go to load Balancer Create A Load Balancer.
2) While Creating Provide All the subnets that are available and provide security & target group.
3) Once Done Create the Load Balancer & Verify the Load Balancer is handling 2 different machines or not.

Click [here to view the Solution](solution_lb.md)
