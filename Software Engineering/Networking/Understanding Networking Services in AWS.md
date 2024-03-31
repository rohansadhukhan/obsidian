
## VPC
**Amazon VPC** is a network service that **logically isolates resources**. It allows users to create an isolated network within the AWS Cloud and provides control over the network environment. Users can customise IP address ranges, configure routing tables, and manage network gateways. VPCs enable secure, scalable, and flexible deployment of AWS resources like EC2 instances and RDS databases.

VPC uses subnets to further segment the network to isolate and manage resources separately.

![[vpc-and-subnets.png|700]]

## Subnet
A **subnet** is a **segmented portion of an IP network**, *allowing for better organisation and security*. It divides a larger network into smaller, more manageable units. Subnets facilitate efficient resource allocation and communication between devices within the same subnet.

There are two types of subnets, 
### Public subnet
A **public subnet** in AWS is a VPC segment with **direct internet access**. It typically hosts resources like EC2 instances that require public access. *Public subnets have a route to an internet gateway, allowing instances to send and receive traffic directly from the internet.*

### Private subnet
A **private subnet** in AWS is a VPC section that **does not have direct internet access**. It hosts resources like databases or internal services that don’t require public access. If needed, *instances in a private subnet can communicate with the internet through a **NAT gateway**.* 




## Route table
An AWS **route** defines **how traffic is directed within the virtual network**. It specifies the path data packets take when traveling between subnets, the internet, and other network resources. Routes are configured in route tables and determine the next hop for each destination, ensuring proper communication between network components.

A **route table** in AWS VPC is a set of rules that determines the path of network traffic within the virtual network. It specifies how traffic is directed between subnets, internet, and other network resources. Each subnet in a VPC is associated with a route table, allowing for customized routing configurations. Route tables are used for communication within the VPC.

To connect to the internet, every VPC requires an AWS internet gateway.

## Internet gateway
An AWS **internet gateway** is a VPC component that **connects a VPC to the internet**. It allows resources within the VPC to communicate with the internet directly. An internet gateway enables services like EC2 instances with public IP addresses to connect to the internet.

An internet gateway also allows resources in a public subnet to directly access the internet, while resources in a private subnet require a NAT gateway to connect to the internet.

## NAT gateway

An AWS **NAT gateway** is a service that **allows private subnet resources to access the internet while keeping them secure**. It acts as an intermediary for outbound traffic, providing a source IP address associated with the NAT gateway. *It enables private instances to communicate with the internet while maintaining security and control within the VPC*.

![[complete-vpc.png|700]]


> ***A single route table can be used for the entire Virtual Private Cloud (VPC) if all public subnets point to the single VPC internet gateway and require no more complex routing rules. Otherwise, each subnet can have its own route table, with a 1 to 1 relationship between route tables and subnets.***

## Security Group
A **security group** controls the inbound and outbound traffic for an associated resource. In other words, it acts as a firewall for the resource.

























































## Resources
1. https://cidr.xyz/