sudo firewall-cmd --permanent --add-port=6443/tcp
sudo firewall-cmd --permanent --add-port=10250/tcp
sudo firewall-cmd --permanent --add-port=179/tcp    # Calico BGP
sudo firewall-cmd --permanent --add-port=4789/udp   # VXLAN
sudo firewall-cmd --permanent --add-port=5473/tcp   # Calico etcd
sudo firewall-cmd --reload

