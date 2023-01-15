# Local Installation Setup

## KUBECTL
Kubectl adalah Kubernetes Command Line Interface (CLI) sehingga user dapat mengakses dan mengelola cluster melalui terminal. Berikut cara instalasinya:
Download binary stable release versi terbaru dari kubectl.
```
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
curl -LO "https://dl.k8s.io/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl.sha256"
echo "$(cat kubectl.sha256)  kubectl" | sha256sum --check
sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl
chmod +x ./kubectl
sudo mv ./kubectl /usr/local/bin/kubectl
kubectl version --client
```
## MINIKUBE:

Minikube merupakan salah satu cara instalasi Kubernetes termudah yang ditujukan kepada pemula dan biasa dijadikan sebagai testing atau development environment. Hal ini memungkinkan kita memiliki cluster master dan worker dalam satu VM yang terisolasi. Berikut adalah beberapa yang perlu diperhatikan sebelum melakukan instalasi.

### Prerequisite:
- 2 CPUs atau lebih
- 2GB dari free memory
- 20GB dari free disk space
- Konesi internet
- Container atau virtual machine manager, seperti: Docker, Hyper-V, KVM, Podman, VirtualBox, atau VMware Workstation

### Langkah Instalasi:
Download minikube dari binary official website yang mereka sediakan dan lakukan penginstalan langsung pada direktori binary file tersebut.
```
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/local/bin/minikube
```
Jalankan minikube cluster dengan command start.
`minikube start`

Periksa apabila cluster sudah berjalan dengan baik dan siap digunakan.
`kubectl get node`
