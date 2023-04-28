# HTTP Ingress

The `http_custom_ip` example demonstrates the deployment of an HTTP load balancer.

The demo also creates an origin pool consisting of the `nginx` service running in the AppStack K8s cluster on port 8080.

## Variables

Set the following environment variables:

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
