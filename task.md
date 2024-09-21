Task 1: Setup a 3 Nodes Multi-Zone AKS Cluster Using Terraform

Objective: Set up a 3-node multi-zone Azure Kubernetes Service (AKS) cluster using Terraform.

Steps:
1. Define the Terraform configuration file (main.tf) with the necessary settings for the AKS cluster, including resource group, cluster name, node count, and availability zones.
2. Initialize the Terraform working directory by running terraform init.
3. Create an execution plan using terraform plan to review the changes that will be made.
4. Apply the configuration with terraform apply to create the AKS cluster.
5. Verify the cluster setup using kubectl commands to ensure the nodes and zones are correctly configured.