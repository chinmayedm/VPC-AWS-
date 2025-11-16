
## Build a Virtual Private Cloud

Today's project focuses on Amazon Virtual Private Cloud (VPC), a service that provides an isolated network in AWS for controlling IP ranges, subnets, route tables, and security settings. The project involved creating a secure, isolated network and attaching an internet gateway for public access, enabling proper communication between instances. 

## Details of the project: 
Used Amazon VPC to create a secure network: A logically isolated network was set up for AWS resources.

## Configured subnets and route tables: 
Subnets were used to divide the VPC into smaller segments, and route tables were configured to direct network traffic.

## Attached an internet gateway: 
An internet gateway was added to the VPC, which allowed instances in the public subnet to communicate with the internet.

## Enabled proper networking: 
This ensured that instances could communicate effectively with each other. 

## Unexpected challenge: 
The level of detail required for optimal security and connectivity in the route table configuration was surprising. 



## VPC
Virtual Private Clouds (VPCs)
VPCs are isolated network environments within a public cloud. They give users the ability to define and control their own networking setup, including subnets, route tables, and security groups. This ensures a secure and scalable cloud infrastructure. 

## Default VPC

A default VPC is automatically created in every AWS account, as AWS provides this to enable easy deployment of resources with basic networking. This includes pre-configured subnets, route tables, and internet access. 

## IPv4 CIDR block
To set up a VPC, you must define an IPv4 CIDR block. This is a range of IP addresses allocated for your network, which helps segment and manage IP assignments within the VPC and prevents address conflicts between resources. 




## Subnets
Subnets are smaller, segmented networks within a Virtual Private Cloud (VPC) that organize and control the flow of traffic. 

## Default subnets
When an AWS account is created, a default VPC and a default subnet for each Availability Zone (AZ) in the region are also created automatically. Distributing resources across subnets in multiple AZs is a strategy for creating a highly available and fault-tolerant architecture. 

## Auto-assign Public IPv4 addresses
This subnet setting ensures that any instance launched within that subnet automatically receives a public IPv4 address. The public IP allows the instance to communicate with the internet without needing a manual IP assignment. 

## Public vs. private subnets
The distinction between public and private subnets is determined by their accessibility from the internet. 

## Public subnet: 
A subnet is considered public if it is associated with a route table that directs traffic to an Internet Gateway, which allows for external access.

## Private subnet: 
A private subnet does not have a route to an Internet Gateway. Instances in a private subnet can only access the internet through a Network Address Translation (NAT) gateway located in a public subnet. 
## Internet gateways (IGW)
An internet gateway is an AWS component that provides a logical connection between a Virtual Private Cloud (VPC) and the internet. 
## Functionality and communication
The internet gateway allows traffic to flow between the VPC and the internet.
## Subnet traffic: 
It enables instances in a public subnet to communicate with the internet. This is essential for hosting public-facing resources.
## Two-way traffic: 
It facilitates both inbound connections (from the internet to the VPC) and outbound connections (from the VPC to the internet) for resources with public IP addresses. 
## Implementation and requirements
 One gateway per VPC: 
Each VPC can have only one internet gateway attached to it.

Gateway-to-VPC attachment: 
The internet gateway must be attached to the VPC to enable internet access.

Route table configuration: After attachment, the public subnet's route table must be configured to direct internet-bound traffic to the internet gateway.

Public IP addresses: Instances in a public subnet require a public IPv4 address or an IPv6 address to communicate with the internet via the gateway.

Consequences of missing a step: If the internet gateway is not attached to the VPC, instances in the public subnets will not be able to connect to or receive traffic from the internet.
