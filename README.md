# terraform-eks-cluster


This is a Terraform project that creates an Amazon EKS (Elastic Kubernetes Service) cluster on AWS. Here's what it does:

Project Overview
This infrastructure-as-code project provisions a complete Kubernetes cluster environment with:

Core Components
VPC Infrastructure (vpc.tf):

Creates a VPC with CIDR 172.20.0.0/16

3 private subnets for worker nodes

3 public subnets for load balancers

NAT gateway for internet access

Proper Kubernetes tags for subnet discovery

EKS Cluster (eks-cluster.tf):

Kubernetes version 1.27

Two managed node groups with t3.small instances

Node group 1: 1-3 nodes (desired: 2)

Node group 2: 1-2 nodes (desired: 1)

Public API endpoint access

Configuration:

Region: us-east-1 (configurable)

Cluster name: vpro-eks (configurable)

Remote state: Stored in S3 bucket "terra-eks12"

Key Features
Uses official AWS Terraform modules for reliability

Follows AWS best practices for EKS networking

Supports auto-scaling worker nodes

Configured for both internal and external load balancers

Usage
Configure AWS credentials

Update variables in variables.tf if needed

Run terraform init, terraform plan, terraform apply

This setup is ideal for development/testing Kubernetes workloads on AWS with a cost-effective t3.small instance configuration.