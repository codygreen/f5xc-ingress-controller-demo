# F5 Distributed Cloud (XC) Ingress Controller Demo

Demonstrate deployment of HTTP load balancer via the F5 Distributed Cloud Ingress Controller

This lab requires:

- XC AppStack Cluster (K8s)
- [XC Ingress Controller](https://gitlab.com/volterra.io/f5xc-ingress-helm/-/tree/main/f5xc-ingress-controller) installed on AppStack Cluster
- Example service in the K8s cluster, such as NGINX
- TLS certificate and key for HTTPS examples

## Examples

- [HTTP Ingress](http/README.md)
- [HTTPS Ingress](http/README.md)
- [HTTP Ingress with a custom IP address](http_custom_ip/README.md)
- [HTTPS Ingress with a custom IP address](https_custom_ip/README.md)
