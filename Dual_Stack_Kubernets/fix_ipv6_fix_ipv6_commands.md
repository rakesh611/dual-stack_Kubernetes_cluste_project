# Assign IPv6 addresses and restart Calico pods

```bash
NODE_NAME=$(hostname)

case "$NODE_NAME" in
  kubemaster.lab.example.com) IPV6_ADDR="fd00:10:244::20/64" ;;
  kubeworker1.lab.example.com) IPV6_ADDR="fd00:10:244::21/64" ;;
  kubeworker2.lab.example.com) IPV6_ADDR="fd00:10:244::22/64" ;;
  *) echo "Unknown node name"; exit 1 ;;
esac

sudo nmcli connection modify enp1s0 ipv6.addresses "$IPV6_ADDR"
sudo nmcli connection modify enp1s0 ipv6.method manual
sudo nmcli connection up enp1s0
sudo systemctl restart NetworkManager

kubectl delete pod -n calico-system --all

