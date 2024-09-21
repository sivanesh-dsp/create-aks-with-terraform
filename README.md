<h1> Creating AKS Cluster </h1>

1. Initialize Terraform:
```
terraform init
```
2. Create Terraform Execution Plan:
```
terraform plan -out main.tfplan
```
3. Apply Terraform Execution Plan:
```
terraform apply -auto-approve main.tfplan
```
4. Verify the results:
```
az aks get-credentials --resource-group $(terraform output -raw resource_group_name) --name $(terraform output -raw kubernetes_cluster_name) --overwrite-existing
kubectl get pods
```
<h1>Simple Deployment</h1>   

1. create a deployment service
```
kubectl create deployment speed --image=sivaneshdsp/speed-test:latest --replicas=3
```
This creates a deployment service using a container image from dockerhub with replica sets of 3

2. Expose to external world
```
kubectl expose deployment speed --type=LoadBalancer --port=80 --target-port=80
```
3. Check Deployment is ready
```
kubectl get deployment
kubectl get services
```

<h1>Clean up</h1>

1. Create destory plan
```
terraform plan -destroy -out main.destroy.tfplan
```
2. Apply Destory plan
```
terraform apply main.destroy.tfplan
```