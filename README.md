# Kubeflow---Natural-Language-Processing
## Version
* Docker：20.10.7
* Kubectl：v1.20.1
* Minikube：v1.20.0
* Kubeflow：v1.3

If you install kubeflow v1.3, you can skip the install.

## Install
### Change the < user > to your own
```Bash
usermod -aG docker <user>
```

```Bash
KUBEFLOW_ROOT=/home/<user>/kubeflow
KF_NAME=v1.3
KF_DIR=${KUBEFLOW_ROOT}/${KF_NAME}
```
  
1.
```Bash
sudo chmod +x docker.sh
sudo chmod +x minikube.sh
sudo chmod +x kubeflow.sh
```
or
```Bash
sudo chmod +x *
```

## Docker
