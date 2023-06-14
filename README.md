#  Multi-Agent-Jenkins-Deployment-Project

This is a Jenkins deployment with two agents, one for the master and the other for the slave. The deployment is on a Kubernetes cluster with both the master and slave on the same node. The slave uses the Docker socket of the master agent, and both agents are in the same namespace.

This type of deployment is ideal for small teams or organizations that do not need a large-scale Jenkins environment. It is also a good option for organizations that want to test out Jenkins before committing to a larger deployment.
<ol>
  <li>Install Kubernetes. You can create a Kubernetes cluster on a cloud provider like Amazon Web Services (AWS), Google Cloud Platform (GCP), Microsoft Azure, or a local cluster using minikube.
  </li>
  <li>Create a namespace. A namespace is a way to isolate your Jenkins deployment from other deployments on the same cluster. 
    <pre> kubectl apply -f namespace.yaml </pre>
  </li>
  <li> Create the master deployment. The master deployment is responsible for running the Jenkins master server.
    <pre> kubectl apply -f service.yaml serviceAccount.yaml volume.yaml deployment.yaml </pre> 
  </li>
  <li> Install Jenkins slave on the slave node.
    <pre> kubectl apply -f slave-svc.yaml slave-deploy.yaml </pre>
  </li>
  <li> Configure the master node for first use. This includes setting up the Jenkins user account, creating the initial Jenkins configuration, and installing any required plugins. You can configure the master node using the Jenkins web interface.
  </li> 
  <li> Configure Jenkins master to use the slave agent and set the executors to 0 in the master node to prevent any building on the master node.  
  </li>
</ol>
