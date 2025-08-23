# Dual-Stack Kubernetes Cluster

This repository contains **commands and configurations** to set up a **Kubernetes cluster with dual-stack networking (IPv4 + IPv6)** using Calico CNI.

## Prerequisites

- CentOS 9 or similar
- kubeadm, kubelet, kubectl installed
- containerd runtime configured
- Firewalld enabled

## Structure

- `hosts/` → Hosts file configuration examples
- `kubeadm/` → Kubeadm commands and kube-proxy config
- `calico/` → Calico operator, custom resources, and IP pools
- `fix-ipv6/` → IPv6 configuration commands
- `firewall/` → Firewall commands
- `busybox-ping-test.md` → Commands to test IPv6 connectivity
