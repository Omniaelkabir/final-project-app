# final-project-app

This application will be build and 
pushed to the DockerHub and deployed 
to the GKE-Cluster.


we will create pipeline 
which will auto Build&Deploy the code inside the application repo:

Add credentials to the DockerHub into Jenkins server :

1) from manage jenkins select manage credentials then add credentials
To add docker user

2) Configure the cluster inside the pod for deploying the new apps:

        1- connect to the pod
        2- install gcloud inside the pod
        3- Switch to jenkins user and authenticate the gcloud within the user and then configure cluster with the user profile
        4- Connect to cluster 
        5- Exit from jenkins user and jenkins pod

3) Create namespace dev

4) Create an Item "Pipeline" from the jenkins server

5) Build your pipeline that you created

6) from the terminal of the VM-instance:

          kubectl get po -n dev
          kubectl get svc -n dev

7) get the ip address

8) get access to the web-site

![Screenshot from 2023-02-24 20-03-50](https://user-images.githubusercontent.com/88335759/221298756-6e42ab93-d1ff-4619-b880-e36e2792ef84.png)
