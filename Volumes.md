### Volumes

- K8s wont provide data persistent by default. When my-sql Pods are restarted the data is lost
- Storage is required that does not depend on the Pod Lifecycle
- Storage should be present on all the nodes so the Pods that are restarted can read the data from Storage.
- Storage needs to survive even when cluster crashes


## Persistent Volume

- Its a cluster resource just like RAM or CPU thats used to store data
- created using YAML files
- Within the PV spec the Storage can be attached like NFS, Cloud provider storage system etc
- Storage classes are associated with PVs defined 
- PVs are not NAMESPACED they are available to the whole cluster to all the namespaces
- Application data is stored in PVs

## Persistent Volume Claim

- Created using YAML configuration
- PVC asks for the type of storage and whichever PV that satisfies the claim will be used
- Within Pods spec we need to have the volumes that references the Persistent Volume Claim
- Pods consume node resources similarly PVCs consume PV resources
- PVCs can request specific sizes and access modes.
- Claims must be in same NAMESPACE

Pods request the vol using PVC -> Finds Volume in Cluster that satisfies the claim(like size) -> Volume will have actual storage backend. 

Note: There can be multiple volume types defined for a Pod.

## Storage Class 

- Define class of storage that is backed by a Provisioner
- Contains, 
    * Provisioner - like AWS EBS
    * Parameters - what type of storage of AWS EBS 
    * reclaim Policy

Pods request the vol using PVC -> PVCs request storage from SC -> SC creates PV that satisfies the claim -> Volume will have actual storage backend.     