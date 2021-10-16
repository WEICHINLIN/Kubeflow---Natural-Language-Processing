# Version

* Docker：20.10.7
* Kubectl：v1.20.1
* Minikube：v1.20.0
* Kubeflow：v1.3

> If you install kubeflow v1.3, you can skip the install.

# Install

### Step 1：Change the < user > to your own
* docker.sh
```Bash
usermod -aG docker <user>
```
* kubeflow.v13.sh
```Bash
KUBEFLOW_ROOT=/home/<user>/kubeflow
KF_NAME=v1.3
KF_DIR=${KUBEFLOW_ROOT}/${KF_NAME}
```
### Step 2：Give execution permission
```Bash
sudo chmod +x docker.sh
sudo chmod +x minikube.sh
sudo chmod +x kubeflow.sh
```
or
```Bash
sudo chmod +x *
```
### Step 3：Execution
```Bash
sudo docker.sh
```
reboot VM or computer.
```Bash
sudo minikube.sh
```
```Bash
sudo kubeflow.sh
```
### Step 4：Port-forward
After all the pods are running
```Bash
kubectl port-forward -n istio-system svc/istio-ingressgateway 8080:80
```
Input in the browser
```Bash
http://localhost:8080/
```
or
```Bash
127.0.0.1:8080
```
<img src="https://github.com/WEICHINLIN/Kubeflow---Natural-Language-Processing/blob/main/image/login.png" width="350" height="200" alt="Login Picture"/><br/>
* Email Address：user@example.com
* Password：12341234

> There may be several pods that are not running, as long as you can login and use it normally, don't worry about it. \
> If Step 3：Execution cannot be executed normally, you can open the file and execute it line by line.

# Docker

> I have provided a public docker image. < m10913018/nltk env:1.0.0 > \
> There are only python packages and html files inside, no code related to natural language processing.

<img src="https://github.com/WEICHINLIN/Kubeflow---Natural-Language-Processing/blob/main/image/http.png" width="300" height="200" alt="Http Picture"/><br/>

> You can customize the web page and remake the docker image.

# Jupyter Notebook - Natural Language Processing

> Please put the files in Jupyter into the folder of Jupyter Notebook first. \
> If you use Minikube to install Kubeflow, the folder of Jupyter Notebook will usually be in：
```Bash
/tmp/hostpath-provisioner/kubeflow-user-example-com/<your Jupyter name>
```
## Flow Chart
<img src="https://github.com/WEICHINLIN/Kubeflow---Natural-Language-Processing/blob/main/image/flow%20chart.png" width="1200" height="200" alt="Flow Chart"/><br/>
> The files in the ZIP are the files generated after the code is executed.

## Custom data
> Twitter-5000-nltk and Cornell-1000-nltk use similar code, and the difference is in downloading and reading data. \
>If you want to use other data, you only need to classify the data and save it in str format into pos_tweets and neg_tweets. \

<img src="https://github.com/WEICHINLIN/Kubeflow---Natural-Language-Processing/blob/main/image/data%20list.png" width="1200" height="200" alt="Flow Chart"/><br/>

# Port Forward

### Step 1：Find the pod name of Http port
<img src="https://github.com/WEICHINLIN/Kubeflow---Natural-Language-Processing/blob/main/image/nltk.jpg" width="1000" height="500" alt="Pipeline"/><br/>
### Step 2：Port-forward
```Bash
kubectl port-forward -n kubeflow-user-example-com <pod name> 3000:5000
```
<img src="https://github.com/WEICHINLIN/Kubeflow---Natural-Language-Processing/blob/main/image/port%20forward.png" width="750" height="300" alt="Pipeline"/><br/>
### Step 3：Input in the browser
```Bash
http://localhost:3000/
```
or
```Bash
127.0.0.1:3000
```
<img src="https://github.com/WEICHINLIN/Kubeflow---Natural-Language-Processing/blob/main/image/nice%20to%20meet%20you.png" width="450" height="200" alt="Http Picture"/><br/>
### Step 4：Predict
<img src="https://github.com/WEICHINLIN/Kubeflow---Natural-Language-Processing/blob/main/image/predict.png" width="800" height="300" alt="Http Picture"/><br/>
