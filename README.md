# K8S-dashboard
How to create k8s dashboard for monitoring

## Create file recommended.yaml, ada 2 cara :
## 1. Menggunakan kubectl

```
$ kubectl apply -f https://raw.githubusercontent.com/kubernetes/dashboard/v2.0.5/aio/deploy/recommended.yaml
```

## 2. Download terlebih dahulu

```
$ curl -o recommended.yaml https://raw.githubusercontent.com/kubernetes/dashboard/blob/master/aio/deploy/recommended.yaml
```

create file recommended.yaml
```
$ kubectl apply -f recommended.yaml
```

## Create file eks-admin-service-account.yaml

```
$ kubectl apply -f eks-admin-service-account.yaml
```

## Execute command dibawah untuk mendapatkan token untuk login ke k8s dashboard

```
$ kubectl -n kube-system describe secret $(kubectl -n kube-system get secret | grep eks-admin | awk '{print $1}')
```
![image](https://user-images.githubusercontent.com/80587939/131612245-5cb0d17a-f639-4858-81fd-fa66fc40a6d3.png)


## referensi
https://docs.aws.amazon.com/eks/latest/userguide/dashboard-tutorial.html
