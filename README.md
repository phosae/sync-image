# sync docker images

sync unavailable docker images to some place pullable 

add new tasks to .github/workflows/tasks.yaml

```yaml
...
jobs:
  sync:
    runs-on: ubuntu-latest
    steps:
    - name: sync multus-cni
      uses: titenkov/docker-sync-action@v1
      with:
        source: ghcr.io/k8snetworkplumbingwg/multus-cni
        destination: myrepo/multus-cni
        destination-credentials: myrepo:${{ secrets.DOCKERHUB_TOKEN }}
```

more options at [titenkov/docker-sync-action](https://github.com/titenkov/docker-sync-action)