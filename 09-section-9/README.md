# Section 9

Install the metrics server before we can perform horizontal pod scaling.

```bash
kubectl top pods -n grade-submission
```

The above command is used to display the memory & cpu usage of pods in the grade submission namespace.