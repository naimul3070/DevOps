## Welcome to Kubernetes Full deployment 

<p> Kubernetes is an open-source container orchestration system for automating software deployment, scaling, and management. Google originally designed Kubernetes, but the Cloud Native Computing 
Foundation now maintains the project </p>

## First Step:

### <a href="https://github.com/ibosbd/devops/tree/main/kubernetes-full-process/Kubernetes">*How to install kubernetes master node(kubernetes)</a> 

### <a href="https://github.com/ibosbd/devops/tree/main/kubernetes-full-process/Kubernetes">*How to install kubernetes worker node (kubernetes)</a>

### <a href="https://github.com/ibosbd/devops/tree/main/kubernetes-full-process/MetalLB_Load_Balancer">*How to install MetalLLB for Loadbnlancing(MetaLLB_Load_blancer) </a>

### <a href="https://github.com/ibosbd/devops/tree/main/kubernetes-full-process/Install%20Helm">*How to install Helm (Helm Install) </a>

### <a href="https://github.com/ibosbd/devops/tree/main/kubernetes-full-process/Install%20Kubernetes%20Nginx%20Ingress%20Controller%20using%20Helm">*How to Install kubernetes Nginx Ingress Controller using Helm (Kubernetes Nginx Ingress Controller using Helm)</a>

## Second Step 

### *How to create secret (below the process >>> # Create Secret ) 

### *How to create ingress rules and execute it (below the process >>> # Create ingress rules and execute )


# Create Secret
### If want to add ssl/tls 
#### upload cert.pem and private_key.pem file in your /home/user directory then execute the command 
	kubectl -n staging create secret tls ibosio-ingress-tls --key private_key.pem --cert cert.pem

# Create ingress rules and execute 
#### Create a yaml file like ibos_ingress.yaml and write configuration rules and save it
    kubectl -n staging apply -f ibos_ingress.yaml
    
# For expose to azure with public ip
    rm /etc/kubernetes/pki/apiserver.*
    kubectl -n staging create secret docker-registry dockercred --docker-server=https://index.docker.io --docker-username=xxxx --docker-password=xxxxx --docker- email=xxxx@gmail.com
    docker rm `docker ps -q -f 'name=k8s_kube-apiserver*'`
    
# kubernates secret token 
    kubectl config view --raw
    
	
## Basic Command 
	
	helm version
	helm list
	helm -n staging  list
	helm -n staging  repo list
	helm -n staging  repo update
	
	kubectl delete node
	kubectl get node
	kubectl get ns
	kubectl get namespaces
	
	kubectl get pods
	kubectl -n staging get pod
	kubectl -n staging get all
	kubectl -n staging get svc
	kubectl -n staging describe pod
	kubectl get pods --all-namespaces
	kubectl get pods --namespace staging
	
	kubectl -n staging get ingressclass
	kubectl -n staging get ingressclass -o wide
	
	kubectl -n metallb-system describe configmap config
	kubectl -n metallb-system get  configmap config -o yaml
	kubectl -n metallb-system describe configmap config
	
	

<img src="https://user-images.githubusercontent.com/43438240/172047801-2d4e8dde-edae-499a-a12c-f7d12b911e00.png" width="200" height="100" />

## If somehow we need to reset full system for reconfiguration then execute the shell Remove.sh
#### Don't execute the shell without understand [ Dangrous ]
	remove.sh 

#### FOR EASY to remove all  we have sh file. Just run the command

     cd kubernetes-full-process/&&chmod +x remove.sh&&./remove.sh
