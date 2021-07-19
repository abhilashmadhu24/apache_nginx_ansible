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

Output should look like

```
root@server:# ansible-playbook host.yml 

PLAY [remote] ************************************************************************************************************

TASK [Gathering Facts] ***************************************************************************************************
ok: [172.16.21.9]

TASK [Install prerequisites] **********************************************************************************************
ok: [172.16.21.9] => (item=aptitude)

TASK [Install Apache] *****************************************************************************************************
ok: [172.16.21.9]

TASK [Change Apache default port] *****************************************************************************************
ok: [172.16.21.9]

TASK [Install Nginx] ******************************************************************************************************
ok: [172.16.21.9]

TASK [Configure nginx proxy]***********************************************************************************************
ok: [172.16.21.9]

TASK [Removing default Nginx page] ****************************************************************************************
ok: [172.16.21.9]

TASK [Starting new nginx reverse-conf] ************************************************************************************
changed: [172.16.21.9]

TASK [Create document root] ***********************************************************************************************
ok: [172.16.21.9]

TASK [Copy index test page]************************************************************************************************
ok: [172.16.21.9]

TASK [Set up Apache virtualHost] ******************************************************************************************
ok: [172.16.21.9]

TASK [Enable new site] ****************************************************************************************************
changed: [172.16.21.9]

TASK [Disable default Apache site] ****************************************************************************************
changed: [172.16.21.9]

RUNNING HANDLER [Reload Apache] *******************************************************************************************
changed: [172.16.21.9]

RUNNING HANDLER [restart apache] ******************************************************************************************
changed: [172.16.21.9]

PLAY RECAP ****************************************************************************************************************
172.16.21.9                : ok=15   changed=5    unreachable=0    failed=0

```
