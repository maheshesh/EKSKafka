#README.md

The Jenkins file calls eksctl to create a Kubernetes Cluster in EKS
It is assumed that Jenkins is installed & setup

It calls EKSCTL cloudformation template for the creation of cluster, Note that it takes atleast 5 minutes for the 
cluster to be up and running
