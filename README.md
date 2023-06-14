#  jenkins-master-slave-deployment

This is a Jenkins deployment with two agents, one for the master and the other for the slave. The deployment is on a Kubernetes cluster with both the master and slave on the same node. The slave uses the Docker socket of the master agent, and both agents are in the same namespace.

This type of deployment is ideal for small teams or organizations that do not need a large-scale Jenkins environment. It is also a good option for organizations that want to test out Jenkins before committing to a larger deployment.
<ol>
  <li>You need to have a Kubernetes cluster to deploy Jenkins on. You can create a Kubernetes cluster on a cloud provider like Amazon Web Services (AWS), Google Cloud Platform (GCP), or Microsoft Azure.
  <li>You need to create a namespace for your Jenkins deployment. A namespace is a way to isolate your Jenkins deployment from other deployments on the same cluster.
    ```bash
      kubectl apply -f namespace.yaml
    ```
  <li>You need to create the master deployment for your Jenkins deployment. The master deployment is responsible for running the Jenkins master server.
    ```bash
      kubectl apply -f service.yaml serviceAccount.yaml volume.yaml deployment.yaml
    ```
    
</ol>

To build and run the app:
```
  Kubectl apply -f .
```
