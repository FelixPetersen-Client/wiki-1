## User setup
* Change password: `passwd`
* Add user: `adduser username`
* Make user su: `usermod -aG sudo username`

## SSH
* Create public and private keys using `ssh-keygen` on local-host
* Copy pub key to server: `ssh-copy-id -i ~/.ssh/id_rsa.pub remote-host`

### Reverse SSH tunneling
* On destination: `ssh -R 10203:localhost:22 middleuser@middleserver` (10203 is an example port)
* Depending on wether Gateway Port is on on middle:
  * On: On local machine: `ssh destinationuser@middle -p 10203`
  * Off: On middle: `ssh destinationuser@localhost -p 10203`