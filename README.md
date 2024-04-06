# kubernetes-deployment

 

Build the Docker image and push it to a container registry 

docker build -t nodejs . 

 

Runs the nodejs image in a detached mode (-d), mapping port 3000 inside the container to port 3000 on the host (-p 3000:3000) 

docker run -p 3000:3000 nodejs 

 

Create a Deployment named nodejsapp with three replicas running your Node.js application. 

kubectl apply -f deployment.yaml 

 

Use the kubectl apply -f crd.yaml command to apply the CRD YAML to the Kubernetes cluster 

kubectl get crd ---> This will list all the CRDs in your cluster, including the newly installed 

Step 1: Enable Metrics Server 

Make sure Metrics Server is installed and running in the Kubernetes cluster. If it's not already installed, you can install it using the following command: 

kubectl apply -f https://github.com/kubernetes-sigs/metricsserver/releases/latest/download/components.yaml 

Step 2: Write HPA Configuration 

Write an HPA configuration YAML file defining autoscaling behavior based on CPU or memory usage thresholds. 

Step 3: Apply HPA Configuration 

Apply the HPA configuration YAML using the  kubectl apply -f myhpa.yaml 

 

Stress Testing 

Step 1: Define Resource Limits 

Update the Deployment YAML to specify resource requests and limits for CPU and memory. 

Apply the updated Deployment YAML to your Kubernetes cluster: 

kubectl apply -f updeployment.yaml 

 

Now for stress testing use hey tool: 

for sending 1000 requests with 10 concurrent requests to http://loccalhost:3000 

Use command: 

hey -n 1000 -c 10 http://localhost:3000 


 

Success Criteria: 
 									 

●  A functional Kubernetes deployment for the Node.js application.  

 

●  HPA configuration that automatically scales the application based on resource usage.  

 

●  Successful execution of the load test with a recorded screencast demonstrating scaling behavior.  

 


