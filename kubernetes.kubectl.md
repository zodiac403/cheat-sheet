# Kube CTL Cheat Sheet

## Trouble Shooting

### Troubleshooting Pending Pods

[Troubleshooting Walkthrough - Pending Pods](https://managedkube.com/kubernetes/k8sbot/troubleshooting/pending/pod/2019/02/22/pending-pod.html)

### Troubleshooting Pod Failures

Follow the [Troubleshooting Walkthrough - Pod Failure CrashLoopBackOff](https://managedkube.com/kubernetes/pod/failure/crashloopbackoff/k8sbot/troubleshooting/2019/02/12/pod-failure-crashloopbackoff.html) from Managed Kube.

1. List Pods: `kubectl get pods`
2. Describe failed Pod: `kubectl describe pod <POD_NAME>`
3. Inspect logs: `kubectl logs <POD_NAME>`
4. Inspect Liveness probe
