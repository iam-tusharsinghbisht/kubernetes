This project will give you an overview on how to create a standalone pod in a minikube cluster.

The below command are execute in remote ec2 instance(if you already have linux system you can ignore the inital update and intall commands):

1) ssh into instance, update existing packages and install docker, add ubuntu user to docekr group:
'''
$ sudo apt update && sudo apt-get install docker.io -y
'''
'''
$ sudo usermod -aG docker ubuntu
'''

2) Install kubectl and check if it is istalled correctly:

'''
$ sudo snap install kubectl --classic
'''
'''
$ kubectl version
'''
 
3) Install minikube and check if minkube is installed correctly:

'''
$ curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/local/bin/minikube && rm minikube-linux-amd64
'''
'''
$ minikube
'''

4) Start minkiube cluster

'''
$ minikube start
'''

5) Check if the minikube cluster is running:

'''
$ kubectl get nodes:
'''

6) Create a pod.yml file with all the pod details:
'''
$ vi pod.yml
'''

7) Create a Pod based on the pod.yml file and view pod details:
'''
$ kubectl create -f pod.yml
'''
'''
$ kubectl get pods
'''
'''
$ kubectl get pods -o wide
'''

8) ssh into the minkbe cluster and curl the Ip of pod to run the container:
'''
$ minikube ssh
'''
'''
$ curl ip
'''

"For successfull execution you will see a nginx page."

9) Delet the pod:
'''
$ kubectl delete pod nginx
''' 
  