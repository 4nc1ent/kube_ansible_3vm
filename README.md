# Automation ansible script to setup 3 vm ubuntu into 1 kubenetes cluster
Ansible scrip to setup 3 vm into 1 kubernetes cluster (1 master , 2 worker node) 

Credites to digital ocean for the script , im just modified to suit local vm deployement

   *****Need to deploy first:Vm: 3 , Os: Ubuntu server 20.04**

   ****Need to install Ansible on your machine first (this machine is not the VM , its your desktop/machine)**

   ****Take a snapshot of your VM first before start, just in case**

   ****Make sure your VM has internet connectivity**

execution:
1. modified ansible config
   command:
    ```
     sudo nano /etc/ansible/ansible.cfg
      - (uncomment)host_key_checking = False
      - (change) timeout = 60
      - (uncomment)(change)allow_world_readable_tmpfiles = True
    ```
2. create project directory and copy all the file into this folder 

3. change your vm ip inside hosts file 

4. execute the script 
  
   1. step1 create unprivilage user and setup ssh connectivity and off swap  
      ```
       ansible-playbook -i hosts ~/kube-cluster/initial.yml
      ```
  
   2. step2 install kubenetes , docker and its depedency 
      ```
       ansible-playbook -i hosts ~/kube-cluster/kube-dependencies.yml
      ```
  
   3. step3 setup master node
      ```
       ansible-playbook -i hosts ~/kube-cluster/master.yml
      ```
  
   4. step4 setup and joine worker node to master node
      ```
       ansible-playbook -i hosts ~/kube-cluster/workers.yml
      ```
  
  
 done.
  



