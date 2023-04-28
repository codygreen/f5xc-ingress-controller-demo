# HTTP Ingress with a Custom IP Address

The `http_custom_ip` example demonstrates the deployment of an HTTP load balancer on a custom IP address. This use case is useful when you need to host DNS outside of XC and your DNS A record must point to a static IP address in your XC tenant.

The demo also creates an origin pool consisting of the `nginx` service running in the AppStack K8s cluster on port 8080.

## Variables

Set the following environment variables:

- PUBLIC_IP_ADDRESS: the IP address the http load balancer will use for advertisement
- HOSTNAME: the DNS FQDN you want to use for the app
- NAMESPACE: the K8s namespace to apply the secret and ingress resources to

You can also save these variables to a `.env` file and run the following command:

```bash
export $(xargs < .env)
```

## Apply the manifest

To substitute the variables in our manifest, we will leverage `envsubst`:

```bash
cat ingress.yml | envsubst | kubectl -n $NAMESPACE apply -f -
```
