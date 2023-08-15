# Enable ssh key login and disable ssh password login
## Generate ssh key 
`ssh-keygen`
## Copy public key to server
`cat ~/.ssh/fedorakeyrsa.pub | ssh root@192.168.0.101 "mkdir -p ~/.ssh && cat >> ~/.ssh/authorized_keys"`

================OR=============

`cat C:\Users\USERNAME/.ssh/fedorakeyrsa.pub | ssh root@192.168.0.101 "mkdir -p ~/.ssh && cat >> ~/.ssh/authorized_keys"`

## Login to the server
`vim /etc/ssh/sshd_config`
  
  ### find the below line 
  `PasswordAuthentication yes`

  ### change it to 
  `PasswordAuthentication no`

`sudo systemctl restart sshd`

===============OR==============

`systemctl restart ssh`