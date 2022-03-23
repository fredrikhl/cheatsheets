# oc, openshift

```bash
oc login <cluster-url> -u <username>
oc projects  # to list
oc project <name>  # to select
```


## status

```bash
oc status
```


## logs

```bash
oc logs <pod-name> -c <container-name> [-t,--tail=<n>] [-f,--follow]
oc logs <pod-name> --all-containers=true

# service logs
oc get services
oc logs svc/<service>
```


## exec

```bash
# oc get pods
oc exec -it <pod-name> <command>
```
