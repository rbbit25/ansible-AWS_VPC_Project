Create the VPC using ansible. Make sure the code work in every region of AWS. 
Screenshot_517

Requirements
In order to work with Python 2.7.16, install next packages:

yum install ansible -y
amazon-linux-extras install ansible2
yum install python-boto3 -y
yum install python-pip -y
pip install boto awscli
Architecture
Screenshot_522

Dependencies
The architecture of VPC is the core for the project. It is not depended on another team and is not solely built to be region depended, because of the flexibility of the code, it can be easily configured to work in any of the available regions. Make changes in region.yaml file – to build the infrastructure described above.

It is a must to enable DHCP in order to auto-assign Public IPs. DHCP - Dynamic Host Configuration Protocol is a network management protocol used on Internet Protocol networks whereby a DHCP server dynamically assigns an IP address and other network configuration parameters to each device on a network so they can communicate with other IP networks.

Screenshot_526

Flexibility
The project has built with a soft code. Our soft code works flexible with in every region because we have collected all the neccessery codes inside "all.yaml" file. The code should be changed just in region part. For example:

region: "us-west-2"
region: "us-east-1"
region: "eu-west-2"
Steps:
Open file
Change region part
Save file
In your vm run ansible-playbook all.yaml
Issues
This issue you will get when the List of Elasti IPs will be 5. In order to solve the problem, delete one EIPs and run again.
Screenshot_492

To solve the next issue, use #map_public: yes , under each Public Subnet!
Screenshot_491

Screenshot_494
