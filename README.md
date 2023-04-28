# F5 Distributed Cloud (XC) Ingress Controller Demo

Demonstrate deployment of HTTP load balancer via the F5 Distributed Cloud Ingress Controller

This lab requires:

- XC AppStack Cluster (K8s)
- [XC Ingress Controller](https://gitlab.com/volterra.io/f5xc-ingress-helm/-/tree/main/f5xc-ingress-controller) installed on AppStack Cluster
- Example service in the K8s cluster, such as NGINX
- TLS certificate and key for HTTPS examples

## Examples

- [HTTP load balancer](http_lb/README.md)
- [HTTP load balancer with a custom IP address](http_lb_custom_ip/README.md)
- [HTTPS load balancer with a custom IP address](https_lb_custom_ip/README.md)
