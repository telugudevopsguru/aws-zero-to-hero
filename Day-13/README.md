# Setting up Customized VPC.
![Lab - Setting up Customized VPC in telugu - Moole Muralidhara Reddy - Telugu Devops Guru](https://github.com/telugudevopsguru/AWS-Networking-5-Days-Practical-Live-Workshop/blob/cf932e66eda01a938dd054c8b8480d4fc43d086f/Day%201-%20%20AWS%20VPC%20Overview/Images/Lab%20-%20Setting%20up%20Customized%20VPC%20in%20telugu%20-%20Moole%20Muralidhara%20Reddy%20-%20Telugu%20Devops%20Guru.png)

## Step 1: Create the AWS VPC
```xml
Name: Murali-VPC in US East (N. Virginia) us-east-1
CIDR : 10.100.0.0/16
```
## Step 2: Create a 2 public subnets with
```xml
CIDR :10.100.8.0/21
Name: murali-public-subnet-1a

CIDR :10.100.16.0/21
Name: murali-public-subnet-1b

```
## Step 3: Create a 2 private subnets with
```xml
CIDR :10.100.80.0/21
Name: murali-private-subnet-1a

CIDR :10.100.88.0/21
Name: murali-private-subnet-1b

```

## Step 4: Create a 2 app subnets with
```xml
CIDR :10.100.144.0/21
Name: murali-app-subnet-1a

CIDR :10.100.162.0/21
Name: murali-app-subnet-1b

```
## Step 4: Create a 2 data subnets with
```xml
CIDR :10.100.168.0/21
Name: murali-data-subnet-1a

CIDR :10.100.176.0/21
Name: murali-data-subnet-1b

```

## Step 5: Create an internet gateway and attach to Murali-VPC
```xml
Name: Murali-VPC-IGW
```
## Step 6: Create a route table and name it Murali-VPC-Public-RouteTable and attach the public subnets to this RouteTable.
```xml
Name: Murali-VPC-Public-RouteTable
```

## Step 7: Create a route table and name it Murali-VPC-Private-RouteTable and attach the private,app,data subnets to this RouteTable.

```xml
Name: Murali-VPC-Private-RouteTable
```

## Step 8: Add the Internet Gateway route to the Public RouteTable.

```xml
Route Entry

Destination : 0.0.0.0/0
Target : Internet Gateway ID
```

## Step 9: Launch the Linux EC2 instance in the Public Subnet.
## Step 10: Connect to the Linux EC2 instance through Putty or SSH command.

#### Congratulations! You have successfully set up the VPC.

----
### NAT Gateway and NAT Instance in AWS VPC

**NAT (Network Address Translation) Gateway** and **NAT Instance** are used to enable instances in a private subnet to connect to the internet or other AWS services, but prevent the internet from initiating connections with those instances.

#### NAT Gateway

**NAT Gateway** is a managed service provided by AWS that enables instances in a private subnet to connect to the internet. It is highly available and scalable, automatically managed by AWS.

**Key Features of NAT Gateway:**
- **Managed Service:** AWS manages the NAT Gateway, ensuring high availability and scalability.
- **Automatic Scaling:** It automatically scales up to meet bandwidth requirements.
- **Ease of Use:** Simple to set up and requires minimal maintenance.
- **High Availability:** Deployed in a specific availability zone but can be set up with multiple NAT Gateways across different zones for redundancy.

#### NAT Instance

**NAT Instance** is an EC2 instance configured to perform network address translation (NAT) for instances in a private subnet.

**Key Features of NAT Instance:**
- **Customizable:** You can customize the instance to meet specific requirements.
- **Scalability:** Requires manual intervention to scale.
- **Management:** Requires management of instance lifecycle, including updates and monitoring.
- **High Availability:** High availability must be manually configured using scripts or services like Auto Scaling.

### Differences between NAT Gateway and NAT Instance

| Feature                | NAT Gateway                   | NAT Instance                  |
|------------------------|-------------------------------|-------------------------------|
| **Management**         | Managed by AWS                | Managed by the user           |
| **Scalability**        | Automatic scaling             | Manual scaling required       |
| **High Availability**  | Built-in high availability    | User must configure           |
| **Ease of Setup**      | Simple, managed setup         | Complex, user-managed setup   |
| **Cost**               | Pay per hour and data transfer| Pay per instance hour         |
| **Customizability**    | Limited customization         | Highly customizable           |


### Lab Session - Create a NAT Gateway in AWS VPC

1. **Create a NAT Gateway:**
   - Navigate to the VPC dashboard.
   - In the left pane, choose "NAT Gateways".
   - Click on "Create NAT Gateway".
   - Select the public subnet in which the NAT Gateway will be created.
   - Allocate a new Elastic IP for the NAT Gateway.
   - Click on "Create NAT Gateway".

2. **Update Route Tables:**
   - Navigate to the Route Tables section in the VPC dashboard.
   - Select the route table associated with the private subnet.
   - Add a new route with `0.0.0.0/0` as the destination and the NAT Gateway ID as the target.


