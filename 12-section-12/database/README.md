# Database

Version: 16.4.4

Since we're pulling the release for Mongo from an online repository like Bitnami, we need to make helm aware of that.

```bash
helm repo add bitnami https://charts.bitnami.com/bitnami
```

Get the default values using the command

```bash
helm show values bitnami/mongodb > default_values.yaml
```

We can then install this into:

```bash
helm install mongodb bitnami/mongodb --version 16.4.4 -f values.yaml -n mongodb
```

### Connection Deets

Because the mongodb service lives in a different namespace from the rest of the application. We'll have to construct the URI as such:

```
<service-name>.<service-namespace>.svc.cluster.local:<port> # mongodb.mongodb.svc.cluster.local:27017
```

The service information can be found using the command:

```bash
kubectl get service -n mongodb
```