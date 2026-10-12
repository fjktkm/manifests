# Manifests

## Headlamp

Headlamp is deployed to the `headlamp` namespace by Argo CD from the official Helm chart.
The chart version is pinned in `bootstrap/apps/headlamp.yaml`. No ingress is configured.

After Argo CD syncs, access it locally:

```sh
kubectl -n headlamp port-forward svc/headlamp 8080:80
```

Open <http://localhost:8080>. In another terminal, request a short-lived login token:

```sh
kubectl -n headlamp create token headlamp
```

Paste the token into Headlamp's login screen. The official chart gives its `headlamp`
ServiceAccount `cluster-admin` permissions by default, so this login can manage the
entire cluster. Changes made in Headlamp to Git-managed resources may be reverted by
Argo CD's automated sync.
