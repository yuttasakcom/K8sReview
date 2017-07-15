## Kubernetes 101

## สารบัญ
- [Setup on Ubuntu](#setup-on-ubuntu)
- [Install kubectl](#install-kubectl)
- [Gcloud Command](#gcloud-command)

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
`sudo apt install kubectl`

## Gcloud Command
`gcloud auth login`