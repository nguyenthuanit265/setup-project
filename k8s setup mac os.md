# 1. Setup tools
```brew install kubectl```

```brew install minikube```

```minikube start```

```kubectl cluster-info```

```kubectl create namespace dev```

# 2. Setup config local (Open terminal)

```mkdir -p ~/.kube```

```touch ~/.kube/config```

```nano ~/.kube/config --> paste config ```
ex: 
```
apiVersion: v1
clusters:
- cluster:
    certificate-authority-data: <data>
    server: https://your-cluster-endpoint:6443
  name: your-cluster-name
contexts:
- context:
    cluster: your-cluster-name
    user: your-username
  name: your-context-name
current-context: your-context-name
kind: Config
preferences: {}
users:
- name: your-username
  user:
    client-certificate-data: <data>
    client-key-data: <data>
```
chmod 600 ~/.kube/config

#### Check config work ?
```
kubectl config view
kubectl cluster-info
```

#### Kiểm tra context hiện tại đúng là cluster EKS trong config ?
```
kubectl config current-context
```

#### Thử kết nối đến cluster:
```
kubectl get nodes
```

# 3. AWS CLI + plugin AWS IAM authenticator cho kubectl
```
brew upgrade awscli
```

```
brew install aws-iam-authenticator
```

```mkdir -p ~/.aws```

```touch ~/.aws/credentials```

```nano ~/.aws/credentials --> paste config ```

```
[dev_eks_access] 
aws_access_key_id =  
aws_secret_access_key =
region =
output =
```

#### Xong run lệnh: 
```
aws eks get-token --cluster-name kegmil-dev-k8s --profile dev_eks_access 
```

```
aws eks --region ap-southeast-1 update-kubeconfig --name kegmil-dev-k8s --profile dev_eks_access
```

#### Some cmds use:
```
-get po: kubectl get po -n dev
-get logs: kubectl logs job-services-dev-76f7d885b5-6x9h4 job-services -n dev -f
```
