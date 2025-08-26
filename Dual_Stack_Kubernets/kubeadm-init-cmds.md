# Initialize Kubernetes Master (dual-stack)

```bash
sudo kubeadm reset -f

sudo kubeadm init \
  --apiserver-advertise-address=192.168.122.20 \
  --pod-network-cidr=10.244.0.0/16,fd00:10:244::/64 \
  --service-cidr=10.96.0.0/12,fd00:10:96::/112 \
  --control-plane-endpoint=192.168.122.20

mkdir -p $HOME/.kube
sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config
sudo chown $(id -u):$(id -g) $HOME/.kube/config

