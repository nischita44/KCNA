### Services

- in K8s service allows to attach static IP address and DNS names for set of Pods
- and address is persisted even when Pod dies
- they also acts as a load balancer
- Pod without a Service will have dynamic IP address. When Pod dies, so does the IP address
- when service is created K8 will create Endpoint object

## Types of Services

- Cluster IP
 * default
 * using Selector the requests will be sent from Service to the Pod
 * using targePort the request will be sent to that Port which Pod is listening to
 * this is defined in spec as port in Service spec

- Headless
 * for stateful application when we need to send request to a specific Pod like my-sql

- NodePort
    * Allows external traffic
    * The request can be sent directly to the pods which is not secure
    * this is defined in spec as nodePort in Service spec

- LoadBalancer
    * Better alternative to manage external traffic
    * This could be from managed third-party cloud service like AWS Network Load Balancer
    * Well suited for production use
    * NodePort and ClusterIP are created automatically in spec file

## Note: Load Balancer is an extension of NodePort. NodePort is an extension of ClusterIP service.


- External Name