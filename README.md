# Final Helm Lab

## first of all i created a cluster on GCP
![image](https://user-images.githubusercontent.com/47079437/217653985-a6a53978-3edb-4ed2-850b-a07c10519548.png)

## Install SonarQube with helm

### from https://artifacthub.io/packages/helm/sonarqube/sonarqube use this commands
```
helm repo add sonarqube https://SonarSource.github.io/helm-chart-sonarqube

helm install my-sonarqube sonarqube/sonarqube --version 8.0.0+463
```
### to edit default values i created yaml file with 
```
service:
  type: LoadBalancer
  externalPort: 9000
  internalPort: 9000

```
#### run upgrade command

```
helm upgrade -f default_values.yaml my-sonarqube sonarqube/sonarqube
```
![image](https://user-images.githubusercontent.com/47079437/217657594-8289ac36-0fdd-4e90-988e-0bc147dade47.png)

![image](https://user-images.githubusercontent.com/47079437/217656048-827102b3-85c3-4689-aebe-e332bda7387c.png)

### Runing sonarqube screen 

![image](https://user-images.githubusercontent.com/47079437/217665910-3c248bb6-9f14-41fa-9bda-8a33a05c719d.png)

## install Jenkins useing Helm

### from https://artifacthub.io/packages/helm/jenkinsci/jenkins use this commands

```
helm repo add jenkinsci https://charts.jenkins.io/

helm install my-jenkins jenkinsci/jenkins --version 4.3.1
```
### to edit default values i created yaml file with 
```
controller:
  serviceType: LoadBalancer

```
#### run upgrade command

```
helm upgrade -f jenkins_default.yaml my-jenkins jenkinsci/jenkins
```
![image](https://user-images.githubusercontent.com/47079437/217657887-f5fbdc67-c735-4555-b030-8ee9d95329a4.png)

![image](https://user-images.githubusercontent.com/47079437/217657954-c62766c4-3e89-49d6-93eb-aa305e1595ec.png)

### Runing jenkins screen

![image](https://user-images.githubusercontent.com/47079437/217658252-e5cdbffa-fd85-4f96-b3e9-e9ac65bf1628.png)

integrate SonarQube with Jenkins 

* Generate sonar token 

![image](https://user-images.githubusercontent.com/47079437/217660751-3430fafe-52ea-4f78-bbf4-ab6a60674cbe.png)

* create credintial in jenkins

![image](https://user-images.githubusercontent.com/47079437/217661086-8d05c54b-8b97-4a2e-8d7b-9836bb027666.png)
![image](https://user-images.githubusercontent.com/47079437/217661159-92d1df71-b2f3-4a82-b4c8-5fdca505970f.png)

* install sonarqube scanner plugin

![image](https://user-images.githubusercontent.com/47079437/217661546-1a2ac28e-591a-46e6-9c89-93532a109a69.png)

![image](https://user-images.githubusercontent.com/47079437/217661666-631e47a1-db56-4a74-8db3-2f91e61e1988.png)

![image](https://user-images.githubusercontent.com/47079437/217662242-f1c52083-fa5d-446a-b3c0-46685da77b21.png)

* configure sonarqube server

![image](https://user-images.githubusercontent.com/47079437/217662727-4866728a-a92b-46a5-a8ff-c27b4e491686.png)

![image](https://user-images.githubusercontent.com/47079437/217663083-097aad59-edf1-4258-afb7-5541a6b69537.png)




Bonus: add multibranch plugins
