---
title: "VMware Tanzu Kubernetes Grid on vSphere"
date: 2019-09-09T10:18:37+02:00
draft: true
---

Download clusterctl
https://github.com/kubernetes-sigs/cluster-api/releases

Download govc
https://github.com/vmware/govmomi/releases
Download Ubunut OVA
https://storage.googleapis.com/capv-images/release/v1.17.3/ubuntu-1804-kube-v1.17.3.ova
Donwnload capv
https://storage.googleapis.com/capv-images/extra/haproxy/release/v0.6.0/capv-haproxy-v0.6.0.ova

Login with govc:
$ export GOVC_INSECURE=1
$ export GOVC_USERNAME=<AD domain/user>
$ export GOVC_PASSWORD=<AD password>
$ govc session.login -u=vcenter.url/sdk

clusterctl exports
export VSPHERE_USERNAME="admin-user"
export VSPHERE_PASSWORD="admin-user-password"

Steps:

Install clusterctl
Install govc
Import VMs
Generate Snapshot Name (root)
Convert to Templates
Create yaml
  VSPHERE_USERNAME: "cloudadmin@vmc.local"
  VSPHERE_PASSWORD: "SuperSecretPassword"

  VSPHERE_SERVER: "10.10.10.10"
  VSPHERE_DATACENTER: "SDDC-Datacenter"
  VSPHERE_DATASTORE: "WorkloadDatastore"
  VSPHERE_NETWORK: "sddc-k8-jomann"
  VSPHERE_RESOURCE_POOL: "*/Resources"
  VSPHERE_FOLDER: "/SDDC-Datacenter/vm/Workloads/mannimal-k8s"
  VSPHERE_TEMPLATE: "centos-7-kube-v1.17.3-temp"
  VSPHERE_HAPROXY_TEMPLATE: "capv-haproxy-v0.6.0-rc.2-temp"

Test connection: clusterctl init --infrastructure vsphere --list-images
 Output:
 gcr.io/cluster-api-provider-vsphere/release/manager:v0.6.2
 gcr.io/kubebuilder/kube-rbac-proxy:v0.4.0
 gcr.io/kubebuilder/kube-rbac-proxy:v0.4.1
 quay.io/jetstack/cert-manager-cainjector:v0.11.0
 quay.io/jetstack/cert-manager-controller:v0.11.0
 quay.io/jetstack/cert-manager-webhook:v0.11.0
 us.gcr.io/k8s-artifacts-prod/cluster-api/cluster-api-controller:v0.3.2
 us.gcr.io/k8s-artifacts-prod/cluster-api/kubeadm-bootstrap-controller:v0.3.2
 us.gcr.io/k8s-artifacts-prod/cluster-api/kubeadm-control-plane-controller:v0.3.2
