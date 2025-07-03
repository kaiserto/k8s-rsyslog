#!/bin/bash

kubectl apply -f rsyslog-config.yaml -n kube-system
kubectl apply -f rsyslog-rbac.yaml -n kube-system
kubectl apply -f rsyslog-daemonset.yaml -n kube-system

exit 0

kubectl delete -f rsyslog-daemonset.yaml -n kube-system
kubectl delete -f rsyslog-rbac.yaml -n kube-system
kubectl delete -f rsyslog-config.yaml -n kube-system

