Source : https://docs.tigera.io/calico/latest/getting-started/kubernetes/quickstart

1) Create  master machine Qty 1 ( cpu : 2 core / memory /4gb/disk : 8gb / os : ubuntu 20.04lts). Its minimum requirement
2) Create  slave machine  Qty 2 ( cpu : 1 core / memory /2gb/disk : 8gb / os : ubuntu 20.04lts) . minumum requirement 1 , better 2
3) run the shell script in both master and work noded  - <br>
https://github.com/abhiramdas99/orchestration-tool-k8/blob/main/workspace-setup/by-kubeadm/install_kubeadm.sh

4) change the hostname of all machine <br>
   - host name for mmaster : hostnamectl set-hostname master <br>
   - host name for worker1 : hostnamectl set-hostname worker1 <br>
   - host name for worker2 : hostnamectl set-hostname worker2 <br>

5) Now we are going to create cluster. type the following command in master node -
   - kubeadm init --pod-network-cidr=192.168.0.0/16   
     > Copy the token and paste it into the all worker node.

6) To start the cluster , you need to run the following command as a regular user in master node  
   - mkdir -p $HOME/.kube
   - sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config
   - sudo chown $(id -u):$(id -g) $HOME/.kube/config

7) Now next thing is , we need to set the network configuration among all cluster hence use the command in
   master node - 
     - kubectl apply -f https://github.com/weaveworks/weave/releases/download/v2.8.1/weave-daemonset-k8s.yaml
     
8) Now check the clustered nodes are running or not. Run the following command in master node -
   -  kubectl get nodes
   -  
