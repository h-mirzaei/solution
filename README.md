###
Setup multi master k8s cluster using haproxy as load balancer and calico as k8s network (challenge-solution)

    note: solution has been tested on ubuntu and windows
          solution just require vagrant and vbox
          solution use ansible(local_ansible) as provisioner which obtain automation 

    to do:
        1- setup the environmet by installing vagrant and Virtualbox which is the vm provider selected in my vagrantfile
        2- after installing virtualbox and vagrant you can start the process by vagrant up command
        3- I have writen a vagrantfile which uses ansible as vm.provision. This vagrantfile creates a multi-master kubernetes cluster which has 2 master nodes and 2 worker nodes and a HAproxy
        4- I have writen playbooks for each node (which are placed in kubernetes-setup folder) wchich installs diffrent packages and sets up the cluster
        5- I used HAproxy as load balancer in front of master nodes
        6- after setting up the cluster you should run kubernetes-setup/kubeallconfig-playbook.yml which install the ingress and helm
        7- I used Nginx ingress to serve the deployed application. 
        8- I also wrote deployment for a pre built application which you can find deployment files in kubernetes-setup/ingress
        9- I have writen deployment for sample helloworld maven which is placed in kubernetes-setup\sample-helloworld

###################################################################################################

Setup jenkins as our CI/CD tool via Vagrantfile (jenkins)

    note: solution has been tested on ubuntu and windows
          solution just require vagrant and vbox
          solution use ansible(local_ansible) as provisioner which obtain automation

    to do: 
        1- setup the environmet by installing vagrant and Virtualbox which is the vm provider selected in my vagrantfile
        2- after installing virtualbox and vagrant you can start the process by vagrant up command
        3- I have writen a vagrantfile which uses ansible as vm.provision. This vagrantfile installs jenkins
        4- I have writen a Jenkinsfile  which is placed in HelloWorld sample folder, using this Jenkinsfile we can build the sample HelloWorld maven project and deploy it to kubernetes

###################################################################################################

CI/CD Pipeline (helloworld)

    note: I have used Jenkins to create CI/CD pipeline which builds the code and deploys the project to K8s cluster. I must mention that I have used a public github HelloWorld project as my sample maven project.

    todo:
        1- I have writen a Jenkinsfile which is placed in the root of the project
        2- Create appropriate creditial to connect to repo in github or it can be handled in checkout step in pipeline
        3- Create a pipeline in Jenkins with pipeline script from SCM option to read the Jenkinsfile from project and start the pipeline
        4- I have writen a Dockerfile which is placed in the root of the project and. This image will be used in deployment time in the manifestfile
        5- I have writen deployment for sample helloworld maven which is placed in kubernetes-setup\sample-helloworld


Also With this solution which is a multi-master cluster we can optain a fully HA production setup. In case of in one of our masters the cluster will still work.
