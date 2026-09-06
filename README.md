Admin → Dashboard Ec2
Management Traffic
SSH :22

Dashboard Ec2 -> Dashboard Service
Application Traffic
HTTP :8888

Dashboard Ec2 -> Counting Ec2
Management Traffic
SSH :22

Counting Ec2 -> Counting Service
Application Traffic
HTTP :9002

PORT=8888 COUNTING_SERVICE_URL="count-private-ip:9002" ./dashboard-service

AWS Environment & Implementation
- Create VPC for the application environment.
- Divide the VPC into a public subnet and a private subnet.
- Connecte the VPC to the Internet through an Internet Gateway.
- Create a route table for the public subnet and linked it to the Internet Gateway.
- Create a separate route table for the private subnet.
- Create dashboard-sg to control access to the Dashboard EC2.
- Create counting-sg to protect the Counting EC2 in the private subnet.
- Deploy the Dashboard service on EC2 instance in the public subnet.
- Deploy the Counting service on EC2 instance in the private subnet.
- Assign an Elastic IP to the Dashboard EC2 for stable public access.
- Start the Dashboard application on port 8888.
- Start the Counting application on port 9002.
- Establish communication between Dashboard and Counting using the private VPC network.
- Use the Dashboard EC2 as a jump host to SSH into the private Counting EC2.
