  Hi All,
  
  This is a simple ansible playbook for installing apache webserver on ubuntu remote hosts with nginx as reverse proxy.
  
  Pre-requisites: Ubuntu 18.04 + Ansible 2.6 on master server
                  Ubuntu 18.04 on remote servers with ssh key autthetication
                  
  Steps: 
  
  ```
  >> apt get install ansible
  >> git clone https://github.com/abhilashmadhu24/apache_nginx_ansible.git
  >> cd apache_nginx_ansible
  >> Edit inventory file and put remote servers details 
  >> Edit vars/default.yml and put domain details.
  >> ansible-playbook host.yml
 ```
