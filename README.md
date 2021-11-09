# WAT

Hosts a set of docker utility containers that are required before bootstrapping a k8s cluster.

## Chartmuseum

After starting the stack, you need to adjust the storage permissions [bug](https://github.com/helm/chartmuseum/issues/241#issuecomment-783167646)

```bash
docker-compose exec -u root chartmuseum sh -c 'chown 1000:0 -R /charts/'
```

This needs to be done only once
