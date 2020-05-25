# A Jenkins job is setup with two stages
1) To deploy the Kafka on EKS
2) To test the deployed Kafka pods. Please note that this stage is not completed, but the idea is for you to pass a bunch of messgaes to the broker and assert that the messages have be consumed successfully

cd DeployKafkaEKS/variants/dev-small
kubectl apply -k
This command useds kustomize to apply a bunch of yamls all throug the code. 
We can utilize the same concept if we have different yaml files with their configMaps 
for lets say Staging and Prod encirobments.

What is Kustomize?
Kustomize traverses a Kubernetes manifest to add, remove or update configuration options without forking.
It is available both as a standalone binary and as a native feature of kubectl. kubectl apply -k is used in this case
