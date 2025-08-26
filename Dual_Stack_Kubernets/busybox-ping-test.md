# Create test pods
kubectl run pod1 --image=busybox --restart=Never -- sleep 3600
kubectl run pod2 --image=busybox --restart=Never -- sleep 3600

# Get pod IPv6 addresses
kubectl get pod pod1 -o jsonpath='{.status.podIPs}'
kubectl get pod pod2 -o jsonpath='{.status.podIPs}'

# Ping from one pod to another
kubectl exec -it pod1 -- ping6 <pod2-ipv6>
kubectl exec -it pod2 -- ping6 <pod1-ipv6>

