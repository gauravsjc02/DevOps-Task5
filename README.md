<h1>DevOps-Task5</h1>
<h2>Objective :</h2>

To Integrate Prometheus and Grafana on top of kubernetes.

1.  Deploy them as pods by creating resources like Deployment, ReplicaSet, Pods or Services.

2.  Make their data persistent using Persistent Volume(PV) & Persistent Volume Claim(PVC). 

3.  And lastly, expose the pods so that it can be accessed from the outside world.

<h2>Requirements :</h2>

1. Knowledge of Docker :- How to create Dockerfile.

2. Kubernetes.

3. Prometheus.

4. Grafana.

5. Persistent Volume(PV) & Persistent Volume Claim(PVC).

<h2>My Project :- </h2>

Firstly, I have created the Docker Image using the Dockerfile for both Prometheus and Grafana.

<h3>Prometheus :-</h3>

![prometheus](https://github.com/gauravsjc02/DevOps-Task5/blob/master/task5/prometheus-Dockerfile.png)


<h3>Grafana :-</h3>

![grafana](https://github.com/gauravsjc02/DevOps-Task5/blob/master/task5/grafana-Dockerfile.png)


After creating the Dockerfile, I have pushed them into my dockerhub account and then created the pv and pvc file on minikube.

<h3>Persistent Volume(PV) & Persistent Volume Claim(PVC) for Prometheus :-</h3>

A PersistentVolume (PV) is a piece of storage in the cluster that has been provisioned by an administrator or dynamically provisioned using Storage Classes.

![pv](https://github.com/gauravsjc02/DevOps-Task5/blob/master/task5/pv-prometheus.png)   
 
 A PersistentVolumeClaim (PVC) is a request for storage by a user.

![pvc](https://github.com/gauravsjc02/DevOps-Task5/blob/master/task5/pvc-prometheus.png)


<h3>Persistent Volume(PV) & Persistent Volume Claim(PVC) for Grafana :-</h3>

![pv](https://github.com/gauravsjc02/DevOps-Task5/blob/master/task5/pv-grafana.png)    
![pvc](https://github.com/gauravsjc02/DevOps-Task5/blob/master/task5/pvc-grafana.png)

After creating the pvc's we attach them to the deployment files of prometheus and grafana.

<h3>Prometheus Deployment file :</h3>

![prom](https://github.com/gauravsjc02/DevOps-Task5/blob/master/task5/pod-prometheus.png)

<h3>Grafana Deployment file :</h3>

![gra](https://github.com/gauravsjc02/DevOps-Task5/blob/master/task5/pod-grafana.png)

Here, the deployments have been created using the custom image that I have created and pushed into my DockerHub account.

<h4>Commands to create the above pv and pvc yml file on minikube :</h4>

kubectl create -f  pv-prometheus.yml

kubectl create -f  pvc-prometheus.yml

kubectl create -f  pv-grafana.yml

kubectl create -f  pvc-grafana.yml

<h4>Commands to create the above deployments yml file on minikube :</h4>

kubectl create -f  pod-prometheus.yml

kubectl create -f  pod-grafana.yml


<h4>Lastly, I have exposed the deployments so that it can be accessed from the outside world.</h4>

![exp](https://github.com/gauravsjc02/DevOps-Task5/blob/master/task5/exposing.png)

<h5>After Exposing : </h5>

We get to see the dashboard where the data is persistent.

<h5>Prometheus dashboard : </h5>

![p](https://github.com/gauravsjc02/DevOps-Task5/blob/master/task5/prometheus-Dashboard.png)

<h5>Grafana's dashboard :</h5>

![g](https://github.com/gauravsjc02/DevOps-Task5/blob/master/task5/grafana-Dashboard2.png)










