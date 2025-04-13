## Namespaces

- Mechanism for isolating groups of resources in a cluster

The 4 different namespaces per Default,

to see - kubectl get namespaces

- kube-system
   * This cannot be modified or created by the user
   * The components that are deployed are System processes

- kube-public
   * publicely accessible data
   * A configmap which contains cluster information

- Kube-node-lease
  * contains the heartbeats of the nodes     

- default

# Usecases

- Access and Resource Limits on Namespaces

   Imagine when two different teams will have access to their own Namespaces like Project 1 Namespace and Project 2 Namespace respectively. So, here each team will have secured isolated environment and additionally limit the resources(Storage, CPU) that each namespace consumes because clusters will have limited resources.

- To avoid many teams having same application name within the cluster.

- Resource Sharing: Staging and Development

- Resource Sharing: Blue/Green Deployment


# Create Namespace 

- Creating in configuration file (This is mostly preferred since its better documented and more convenient)
- Using kubectl







