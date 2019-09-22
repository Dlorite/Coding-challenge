# Explanation

I have done 3 parts to show different technologies but with a limted time i have not tested them. 

1. Install Ansible and launch a Jenkins, on this way we can show how to launch a docker container with ansible. 
2. With Jenkinfile i have created a pipeline to test the application and launch the deploy with helm
3. Wiht Helm we install it the application on the cluster of k8s

# Steps to run it:
Create a jenkins with Ansible so you can launch the test

## Ansible
- sudo apt-get update
- sudo apt-add-repository ppa:ansible/ansible
- sudo apt install ansible
- ansible --version

## Jenkins
- ansible-playbook -i hosts linux_jenkins.yml
- Configure jenkins with a linux node with kubectl installed

## 
