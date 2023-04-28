# F5 Distributed Cloud (XC) Ingress Controller Demo

Demonstrate deployment of HTTP load balancer via the F5 Distributed Cloud Ingress Controller

This lab requires:

- XC AppStack Cluster (K8s)
- Example service in the K8s cluster, such as NGINX
- Kustomize installed locally

## HTTP Ingress with a Custom IP Address

The `http_lb_custom_ip` example demonstrates the deployment of an HTTP load balancer on a custom IP address. This use case is useful when you need to host DNS outside of XC and your DNS A record must point to a static IP address in your XC tenant. 

The demo also creates an origin pool consisting of the `nginx` service running in the AppStack K8s cluster on port 8080.

### Variables

Set the following environment variables:


- PUBLIC_IP_ADDRESS: the IP address the http load balancer will use for advertisement
- HOSTNAME: the DNS FQDN you wnat to use for the app
- NAMESPACE: the K8s namespace to apply the secret and ingress resources to


### Apply the manifest

To substitute the variables in our manifest, we will leverage `envsubst`:

```bash
cat ingress.yml | envsubst | kubectl -n $NAMESPACE apply -f -
```

## HTTPS Ingress with a Custom IP Address

The `https_lb_custom_ip` example demonstrates the deployment of an HTTPS load balancer on a custom IP address. This use case is useful when you need to host DNS outside of XC and your DNS A record must point to a static IP address in your XC tenant. 

The demo also creates an origin pool consisting of the `nginx` service running in the AppStack K8s cluster on port 8080.

### Variables

Set the following environment variables:


- PUBLIC_IP_ADDRESS: the IP address the http load balancer will use for advertisement
- HOSTNAME: the DNS FQDN you wnat to use for the app
- TLS_CERT: the base64 encoded certificate
- TLS_KEY: the base64 encoded certificate key
- SECRET_NAME: the name of the K8s certificate secret
- NAMESPACE: the K8s namespace to apply the secret and ingress resources to


### Apply the manifest

To substitute the variables in our manifest, we will leverage `envsubst`:

```bash
cat secret.yml | envsubst | kubectl -n $NAMESPACE apply -f -
cat ingress.yml | envsubst | kubectl -n $NAMESPACE apply -f -
```
