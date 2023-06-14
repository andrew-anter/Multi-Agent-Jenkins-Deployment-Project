#  jenkins-master-slave-deployment

This is a Jenkins deployment with two agents, one for the master and the other for the slave. The deployment is on a Kubernetes cluster with both the master and slave on the same node. The slave uses the Docker socket of the master agent, and both agents are in the same namespace.

This type of deployment is ideal for small teams or organizations that do not need a large-scale Jenkins environment. It is also a good option for organizations that want to test out Jenkins before committing to a larger deployment.


To build and run the app:
```
  Kubectl apply -f .
```
