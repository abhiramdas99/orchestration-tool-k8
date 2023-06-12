Source : https://docs.tigera.io/calico/latest/getting-started/kubernetes/quickstart

1) Create  master machine Qty 1 ( cpu : 2 core / memory /4gb/disk : 8gb / os : ubuntu 20.04lts). Its minimum requirement
2) Create  slave machine  Qty 2 ( cpu : 1 core / memory /2gb/disk : 8gb / os : ubuntu 20.04lts) . minumum requirement 1 , better 2
3) run the shell script in both master and work noded  - <br>
https://github.com/abhiramdas99/orchestration-tool-k8/blob/main/workspace-setup/by-kubeadm/install_kubeadm.sh

4) change the hostname of all machine
   host name for mmaster : hostnamectl set-hostname master 
   host name for worker1 : hostnamectl set-hostname worker1
   host name for worker2 : hostnamectl set-hostname worker2


   
