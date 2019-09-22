# Explanation

I have done 3 parts to show different technologies but with a limted time i have not tested them, here only the structure of itself.

1. Install Ansible and launch a Jenkins, on this way we can show how to launch a docker container with ansible. 
2. With Jenkinfile i have created a pipeline to test the application, we would configure the jenkins to build a new version once it is pushed by the developer, if this is a release candidate
3. Create the new image (Note: The dockerfile is missing but should be there to build the image)
4. Push the image to the repository
5. Wiht Helm we install it the application on the cluster of k8s
6. After the deployment we will monitorize with the monitoring tools, instana and Prometheus and we will check for errors in the logs in ElasticSearch

So we use ansible for the set-up of the infrastructure (in the Adidas case this is not mandatory because a Jenkis is already there), we use Jenkins for create the pipeline with the entire cycle (test it, create the docker image, push it and deploy it in a test cluster), and helm for the deployment on the k8s cluster.

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

## WebPage

I have copied the web page doing a reverse search of the image, in this page you can see it https://www.tomanthony.co.uk/blog/detect-visitor-social-networks/