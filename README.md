# To Do Application
## Project: Deploying a Web Application on Kubernetes

### Overview
This project demonstrates the deployment of a web application on Kubernetes using Docker containers. The project involved containerizing a Flask-based To-Do application with MongoDB, deploying it on a local Kubernetes cluster (Minikube), and then scaling it to AWS EKS. The project also explored Kubernetes features including replication controllers, health monitoring, rolling updates, and alerting.

### Part 1: Creating the Application
- **Application**: Developed a simple To-Do web application using Flask and MongoDB.

### Part 2: Containerizing the Application with Docker
1. **Docker Installation**: Installed Docker from the [official website](https://www.docker.com/get-started).
2. **Dockerfile Creation**: 
   - Created a Dockerfile for the Flask application to set up the working directory, copy application code, and define the command to run the app.
3. **Image Building**: Built the Docker image using the Docker CLI.
4. **Docker Compose**: Developed a `docker-compose.yml` file to define services for the Flask app and MongoDB, including images, ports, and volume mounts.
5. **Push to Docker Hub**: Pushed the Docker image to Docker Hub for deployment.

### Part 3: Deploying on Minikube
1. **Minikube Installation**: Installed Minikube following the [official documentation](https://minikube.sigs.k8s.io/docs/start/).
2. **Minikube Start**: Initiated Minikube to set up a local Kubernetes cluster.
3. **Pod Creation**: Deployed two pods—one for Flask and one for MongoDB.
4. **Kubernetes Deployment**: Configured a deployment specifying the Docker image, replicas, and container ports.
5. **Service Exposure**: Created a Kubernetes service to expose the application.
6. **Testing**: Verified application accessibility via the service URL on Minikube.

### Part 4: Deploying on AWS EKS
1. **EKS Cluster Creation**: Created an AWS EKS cluster using the AWS Management Console.
2. **Kubectl Configuration**: Configured kubectl to connect to the EKS cluster.
3. **Deployment on EKS**: Set up a Kubernetes deployment in EKS with the Docker image and replicas.
4. **Service Exposure**: Exposed the deployment with a Kubernetes service for load balancing.
5. **Testing**: Ensured application accessibility from outside the EKS cluster.

### Part 5: Replication Controller
1. **Replication Controller**: Created a replication controller to maintain a specified number of application replicas.
2. **Configuration**: Defined the desired number of replicas in the configuration file.
3. **Verification**: Verified that the desired number of replicas were running and handled pod failures.
4. **Scaling**: Adjusted the number of replicas and confirmed scaling behavior.

### Part 6: Rolling Update Strategy
1. **Rolling Update Configuration**: Set up the deployment for a rolling update strategy.
2. **Docker Image Update**: Deployed a new Docker image version.
3. **Update Monitoring**: Monitored the rolling update progress using kubectl and Kubernetes Dashboard.
4. **Testing**: Confirmed the application was running with the new Docker image version.

### Part 7: Health Monitoring
1. **Probes Configuration**: Set up liveness and readiness probes for the application.
2. **Failure Action**: Configured Kubernetes actions for probe failures, such as pod restarts.
3. **Health Monitoring**: Monitored pod health using kubectl and Dashboard.
4. **Testing Probes**: Simulated failures to test the health monitoring system.

### Step 8: Alerting 
1. **Prometheus Setup**: Configured Prometheus to receive Kubernetes alerts.
2. **Alert Configuration**: Created alert rules for conditions such as probe failures.
3. **Notification Service**: Integrated Slack for alert notifications.
4. **Testing Alerts**: Verified alerting functionality by simulating a failure.
