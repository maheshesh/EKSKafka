# Quote the owner of the code
- Please note that the code in deployEKS has been forked from Yolean/kubernetes-kafka.
- Thank you Yolean for the detailed instructions and sample code. This has a good reference on how to build a Kafka cluster 

# Repo Structure
- BuildEKSStructure builds an EKS cluster in AWS through a Jenkins job (Refer the Readme.md in the BuildEKS folder). Run the Jenkins Job to create an EKS cluster
- DeployKafkaToEKS deploys the Kafka on EKS. Run the Jenkins Job in this folder to deploy Kafka


# Kafka on EKS
Quikstart to create a simple kafka setup 
- kubectl create namespace kafka && \
- cd /DeployKafkaEKS/variants/dev-small
- kubectl apply -k 

# Points to note on Kafka setup
- Zookeeper also needs to be packaged along with kafka as a seperate PoD 
- Anti Affinity is expected to be setup to ensure ZooKeeper and Kafka are spread across and don't end up together
- Stateful set and Persistant volumes also needs to be setup, this ensures the state of Kafka is preserved in a  
database (to preserve the state if a pod is destroyed and EKS has to rebuild the PoD)
- The liveness (To check if container is running and needs a restart) & readiness (ready to recieve requests) aspects of the Pods needs to be considered

# Alternative solution
- Strinzi is https://strimzi.io/documentation/ is one more open source solution to get Kafka installed on Kubernetes 
