### Ingress

## External service versus Ingress

In a cluster, we have my-app pod and a my-app service which is external service for this, 
in this case application can be accessed from IP address and port number which will be like 
http://124.89.101.2:25671 - this is good for testing 

when we need for production we need to have a domain name 
and secure the connection using https for this we use 
ingress.

https://my-app.com -> my-app ingress -> my-app internal service -> my-app pod


- In the configuration file of ingress we will have kind as Ingress and routing rules,
    * Host - [myapp.com]
    * servicename - [name of internal service]
    This means the path is forwarded from host to service name 

- Ingress creates ingress rules that Controller can evaluate. Rules include hostname/domain name, serviceName , service port.

  * Ingress Rules can have multiple paths for same host.
 For example, Google has same host but we can access different services like analytics, shopping, google drive etc.
  * Ingress Rules can have multiple hosts for different services.

- To configure Ingress in the cluster we need Ingress Controller Pod in the K8s cluster
    Example is Nginx from K8s itself bute there are many other third party which can be used.
    The Ingress Controller,
    * Evaluates all the rules
    * manages redirections
    * entrypoint to the cluster

-   On Public cloud, the requests first goes to the cloud load balancer which is already been setup in most of the cloud providers

   Load Balancers from cloud providers -> Ingress Controller -> [my-app ingress] -> [my-app internal service] -> [my-app pod]




