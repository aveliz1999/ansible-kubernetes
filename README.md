# ansible-kubernetes
Ansible playbook to set up a kubernetes cluster with a few utility deployments.

 - Installs docker in all the nodes
 - Sets up master and worker nodes with kubeadm
 - Installs calico cni
 - Installs metallb load balancer
 - Installs nginx ingress controller
 - Installs metrics-server to collect pod/node usage metrics
 - Installs kubernetes dashboard
 - Installs cert-manager and configures it with let's encrypt production

## Usage

 - `git clone https://github.com/aveliz1999/ansible-kubernetes`
 - `cd ansible-kubernetes`
 - Configure the deployment by changing the variables inside group_vars/master.yaml
	 - Configure pod network cidr, service cidr, metllb ip range, and let's encrypt email
 - Edit the hosts.ini file to add in the IPs of your master and nodes
	 - Ensure that you copy over your ssh key to the master and nodes so that ansible can connect to them
 - `ansible-playbook site.yaml`

