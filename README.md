# 搭建 kubernetes-dashboard

## 1. 安装dashboard：
```
kubectl create -f kubernetes-dashboard.yaml
```
## 2. 获取token：
```
kubectl -n kube-system describe $(kubectl -n kube-system get secret -n kube-system -o name | grep namespace) | grep token
```
## 3. 启动kubernetes-dashboard：
```
kubectl proxy
```
## 4. 访问以下链接时，将获取的token粘贴到输入框中：
```
http://localhost:8001/api/v1/namespaces/kube-system/services/https:kubernetes-dashboard:/proxy/#!/overview?namespace=default
```
 大功告成！ 
