# Kubernetes NodePort Service Example

```
kubectl create -f deployment.yaml
kubectl create -f service.yaml
```
```
kubectl get services,pods -o wide
NAME                 TYPE        CLUSTER-IP       EXTERNAL-IP   PORT(S)          AGE     SELECTOR
service/my-nginx     NodePort    10.101.147.237   <none>        8080:31633/TCP   2m20s   run=my-nginx

NAME                            READY   STATUS    RESTARTS      AGE   IP           NODE     NOMINATED NODE   READINESS GATES
pod/my-nginx-684dd4dcd4-jmj6j   1/1     Running   1 (14m ago)   20m   10.0.1.30    worker   <none>           <none>
pod/my-nginx-684dd4dcd4-x6xq9   1/1     Running   1 (13m ago)   20m   10.0.0.124   cp       <none>           <none>
```
```
curl cp.local:31633
```
