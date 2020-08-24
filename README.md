LAB - Tanzu Challenge
========================

If you already have the eduk8s operator installed and configured, to deploy
and view this sample workshop, run:

```
kubectl apply -f https://raw.githubusercontent.com/eduk8s-tests/lab-tanzu-challenge/master/resources/workshop.yaml
kubectl apply -f https://raw.githubusercontent.com/eduk8s-tests/lab-tanzu-challenge/master/resources/training-portal.yaml
```

This will deploy a training portal hosting just these workshops. To get the
URL for accessing the training portal run:

```
kubectl get trainingportal/eduk8s-tanzu-challenge
```

The training portal is configured to allow anonymous access.
