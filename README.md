# kube_ansible_3vm
Ansible scrip to install 3 vm into 1 kubernetes cluster (1 master , 2 node) 

Credites to digital ocean for the script , im just modified to suit local vm deployement
Vm: 3 
Os:
Ubuntu server 20.04 

need to install ansible first on your local machine (this machine is not vm, it is your laptop/desktop)

execution:
1) modified ansible config
  command
  sudo nano /etc/ansible/ansible.cfg
    change 
    (uncomment)host_key_checking = False
    (change) timeout = 60
    (uncomment)(change)allow_world_readable_tmpfiles = True

2) create project directory and copy all the file into this folder 




