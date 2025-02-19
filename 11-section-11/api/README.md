# API

You can package this directory for helm by running the command:

```bash
helm package .
```

Packaging this helm chart will result in a `.tgz` file being created.
You can then install this helm chart by running the command:

```bash
helm install grade-submission-api grade-submission-api-1.0.0.tgz
```

You can also check that all values are attended to and there aren't any errors with helm templating by running the command:

```bash
helm template .
```

You can then remove all the k8s artifacts by uninstalling the helm chart.

```bash
helm uninstall grade-submission-api
```