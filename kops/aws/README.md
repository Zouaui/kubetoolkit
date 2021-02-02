# KOPS

Create bucket to store states

```
aws s3 mb s3://kube.faycal-zouaoui.fr
```

export env vars 
```
export NAME=kube.faycal-zouaoui.fr
export KOPS_STATE_STORE=s3://kube.faycal-zouaoui.fr
```

create a cluster 

```
kops create cluster --zones=eu-west-1a --name ${NAME} --yes
```

check health 

```
kops validate cluster --wait 10m
```



destroy the cluster 


```
kops delete cluster --name ${NAME} --yes
```