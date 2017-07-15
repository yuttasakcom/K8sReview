## Kubernetes 101

## สารบัญ
- [Setup on Ubuntu](#setup-on-ubuntu)
- [Install kubectl](#install-kubectl)
- [Gcloud Command](#gcloud-command)
- [Begin step](#begin-step)
- [Command line](#command-line)

## Setup on Ubuntu
[Link](https://cloud.google.com/sdk/docs/quickstart-debian-ubuntu)<br>

คำสั่งติดตั้งบน Ubuntu<br>
```
# Create an environment variable for the correct distribution
export CLOUD_SDK_REPO="cloud-sdk-$(lsb_release -c -s)"

# Add the Cloud SDK distribution URI as a package source
echo "deb http://packages.cloud.google.com/apt $CLOUD_SDK_REPO main" | sudo tee -a /etc/apt/sources.list.d/google-cloud-sdk.list

# Import the Google Cloud Platform public key
curl https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo apt-key add -

# Update the package list and install the Cloud SDK
sudo apt-get update && sudo apt-get install google-cloud-sdk
```

## Install kubectl
`sudo apt install -y kubectl`

## Begin step
หลังจากติดตั้ง Tools แล้วให้ทำตามขั้นตอนประมาณนี้
- สมัครสมาชิกลงทะเบียนสร้าง Account [Link](https://cloud.google.com/)
- Create Project
- Create a container cluster
- สร้าง container clusters เสร็จกด Connect button
- เปิด terminal พิมพ์คำสั่ง `gcloud auth login` หรือ `gcloud auth application-default login`
- running the following command
- Then open the Dashboard interface by navigating to the following location in your browser: http://localhost:8001/ui
- เริ่มศึกษาตัวอย่าง 01-08 ดู command ด้านล่างประกอบ


## Command line
```
# gcloud command
gcloud
gcloud components list
gcloud auth login
gcloud auth application-default login
gcloud docker -- pull gcr.io/google-containers/echoserver:1.6

# kubectl command
kubectl create -f 01-pod.yaml
kubectl get pods or kubectl get po
kubectl describe po echoserver or kubectl describe po/echoserver
kubectl port-forward echoserver 9000:8080
kubectl delete -f 01-pod.yaml
kubectl get svc or kubectl get svc --watch
kubectl describe svc echoserver
kubectl run -i -t --rm busybox --image=busybox
kubectl get nodes
kubectl get rs
kubectl get deploy
kubectl set image deploy/echoserver echoserver=gcr.io/google-containers/echoserver:1.6
kubectl rollout status deploy/echoserver
kubectl rollout history deploy/echoserver or kubectl rollout history deploy/echoserver --revision=2
kubectl rollout undo deploy/echoserver
kubectl get -o yaml deploy/echoserver or kubectl get -o yaml all
kubectl get ds
kubectl apply -f 07.resources.yaml
```