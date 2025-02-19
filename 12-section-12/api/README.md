# API

### PACKAGING

You can package this directory for helm by running the command:

```bash
helm package .
```

### INSTALLING

Packaging this helm chart will result in a `.tgz` file being created.
You can then install this helm chart by running the command:

```bash
helm install grade-submission-api grade-submission-api-1.0.0.tgz -n grade-submission
```

### TEMPLATING

You can also check that all values are attended to and there aren't any errors with helm templating by running the command:

```bash
helm template .
```

### UNINSTALLING

You can then remove all the k8s artifacts by uninstalling the helm chart.

```bash
helm uninstall grade-submission-api
```

### UPGRADING

You can upgrade a helm release

```bash
helm upgrade grade-submission-api grade-submission-api-1.0.0.tgz -n grade-submission
```

OR 

```bash
helm upgrade grade-submission-api . -n grade-submission
```

### ROLLBACK

You can rollback to a previous release by getting the revision from the initial message after upgrade.

```txt
Release "grade-submission-api" has been upgraded. Happy Helming!
NAME: grade-submission-api
LAST DEPLOYED: Wed Feb 19 04:05:04 2025
NAMESPACE: grade-submission
STATUS: deployed
REVISION: 2
TEST SUITE: None
```

And run the `helm rollback command` to roll back.

```bash
helm rollback grade-submission-api 2 -n grade-submission
```