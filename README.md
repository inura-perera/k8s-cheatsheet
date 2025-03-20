# Kubernetes Command Cheat Sheet

A comprehensive list of Kubernetes commands categorized by functionality. Use this as a quick reference for managing clusters, workloads, networking, and more.

---

## Table of Contents
- [Cluster Management](#cluster-management)
- [Namespace Management](#namespace-management)
- [Deploying Applications](#deploying-applications)
- [Workloads (Deployments, DaemonSets, ReplicaSets)](#workloads-deployments-daemonsets-replicasets)
- [Pods & Containers](#pods--containers)
- [Services & Networking](#services--networking)
- [Network Policies](#network-policies)
- [Configuration (ConfigMaps, Secrets)](#configuration-configmaps-secrets)
- [Stateful Workloads (StatefulSets, Volumes)](#stateful-workloads-statefulsets-volumes)
- [Storage & Volumes](#storage--volumes)
- [Troubleshooting & Debugging](#troubleshooting--debugging)
- [Advanced Debugging](#advanced-debugging)
- [RBAC (Role-Based Access Control)](#rbac-role-based-access-control)
- [Security & Policies](#security--policies)
- [Resource Management](#resource-management)
- [Autoscaling](#autoscaling)
- [Advanced Commands](#advanced-commands)
- [Custom Resources (CRDs)](#custom-resources-crds)
- [Context & Configuration](#context--configuration)
- [Certificate Management](#certificate-management)
- [Node Operations](#node-operations)
- [Output Formatting](#output-formatting)
- [Plugin Management (krew)](#plugin-management-krew)
- [Utility Commands](#utility-commands)
- [Deprecated/Historical Commands](#deprecatedhistorical-commands)

---

## Cluster Management
| Command | Description |
|---------|-------------|
| `kubectl cluster-info` | Display cluster information |
| `kubectl get nodes` | List all nodes in the cluster |
| `kubectl describe node <node-name>` | Inspect node details |
| `kubectl top node` | Show resource usage for nodes |
| `kubectl cordon <node-name>` | Mark a node as unschedulable |
| `kubectl uncordon <node-name>` | Mark a node as schedulable |
| `kubectl drain <node-name>` | Drain a node for maintenance |

---

## Namespace Management
| Command | Description |
|---------|-------------|
| `kubectl create namespace <ns-name>` | Create a namespace |
| `kubectl delete namespace <ns-name>` | Delete a namespace |
| `kubectl get namespaces` | List all namespaces |

---

## Deploying Applications
| Command | Description |
|---------|-------------|
| `kubectl apply -f <file.yaml>` | Apply a configuration file |
| `kubectl create deployment <name> --image=<image>` | Create a deployment |
| `kubectl delete -f <file.yaml>` | Delete resources from a file |
| `kubectl scale deployment <name> --replicas=<count>` | Scale a deployment |
| `kubectl rollout status deployment/<name>` | Check rollout status |
| `kubectl rollout undo deployment/<name>` | Rollback a deployment |

---

## Workloads (Deployments, DaemonSets, ReplicaSets)
| Command | Description |
|---------|-------------|
| `kubectl get daemonsets` | List DaemonSets |
| `kubectl describe daemonset <name>` | Inspect DaemonSet details |
| `kubectl get replicasets` | List ReplicaSets |
| `kubectl scale replicaset <name> --replicas=<count>` | Scale a ReplicaSet |

---

## Pods & Containers
| Command | Description |
|---------|-------------|
| `kubectl get pods` | List pods |
| `kubectl describe pod <pod-name>` | Inspect pod details |
| `kubectl logs <pod-name>` | Fetch pod logs |
| `kubectl exec -it <pod-name> -- /bin/sh` | Execute a shell in a pod |
| `kubectl port-forward <pod-name> <local-port>:<pod-port>` | Forward ports to a pod |
| `kubectl delete pod <pod-name>` | Delete a pod |

---

## Services & Networking
| Command | Description |
|---------|-------------|
| `kubectl expose deployment <name> --port=<port>` | Expose a deployment as a service |
| `kubectl get services` | List services |
| `kubectl get ingress` | List ingress resources |

---

## Network Policies
| Command | Description |
|---------|-------------|
| `kubectl get networkpolicies` | List network policies |
| `kubectl describe networkpolicy <name>` | Inspect network policy details |

---

## Configuration (ConfigMaps, Secrets)
| Command | Description |
|---------|-------------|
| `kubectl create configmap <name> --from-file=<file>` | Create a ConfigMap |
| `kubectl create secret generic <name> --from-literal=<key>=<value>` | Create a Secret |
| `kubectl get secrets` | List Secrets |

---

## Stateful Workloads (StatefulSets, Volumes)
| Command | Description |
|---------|-------------|
| `kubectl get statefulsets` | List StatefulSets |
| `kubectl get pv` | List PersistentVolumes |
| `kubectl get pvc` | List PersistentVolumeClaims |

---

## Storage & Volumes
| Command | Description |
|---------|-------------|
| `kubectl get storageclass` | List storage classes |
| `kubectl get volumesnapshot` | List volume snapshots |

---

## Troubleshooting & Debugging
| Command | Description |
|---------|-------------|
| `kubectl top pod` | Show pod resource usage |
| `kubectl get events --sort-by=.metadata.creationTimestamp` | View cluster events |
| `kubectl logs <pod-name> --previous` | View logs of a crashed pod |

---

## Advanced Debugging
| Command | Description |
|---------|-------------|
| `kubectl attach -it <pod-name> -c <container>` | Attach to a running container |
| `kubectl debug -it <pod-name> --image=busybox` | Create a debug container |
| `kubectl get events --field-selector type=Warning` | Filter warning events |

---

## RBAC (Role-Based Access Control)
| Command | Description |
|---------|-------------|
| `kubectl get serviceaccounts` | List ServiceAccounts |
| `kubectl get roles` | List Roles |
| `kubectl auth can-i <verb> <resource>` | Check permissions |

---

## Security & Policies
| Command | Description |
|---------|-------------|
| `kubectl get podsecuritypolicies` | List Pod Security Policies (PSPs) |
| `kubectl auth reconcile -f <rbac-file.yaml>` | Reconcile RBAC rules |

---

## Resource Management
| Command | Description |
|---------|-------------|
| `kubectl set image deployment/<name> <container>=<new-image>` | Update container image |
| `kubectl edit deployment/<name>` | Edit a deployment |
| `kubectl patch deployment/<name> -p '{"spec":{...}}'` | Patch a deployment |

---

## Autoscaling
| Command | Description |
|---------|-------------|
| `kubectl get hpa` | List Horizontal Pod Autoscalers |
| `kubectl delete hpa <name>` | Delete an HPA |

---

## Advanced Commands
| Command | Description |
|---------|-------------|
| `kubectl api-resources` | List API resources |
| `kubectl explain <resource>` | Show resource schema |
| `kubectl proxy` | Start API server proxy |

---

## Custom Resources (CRDs)
| Command | Description |
|---------|-------------|
| `kubectl get crd` | List Custom Resource Definitions |
| `kubectl get <custom-resource>` | List custom resources |

---

## Context & Configuration
| Command | Description |
|---------|-------------|
| `kubectl config use-context <context>` | Switch context |
| `kubectl config get-contexts` | List contexts |

---

## Certificate Management
| Command | Description |
|---------|-------------|
| `kubectl get csr` | List CertificateSigningRequests |
| `kubectl certificate approve <csr-name>` | Approve a CSR |

---

## Node Operations
| Command | Description |
|---------|-------------|
| `kubectl taint node <node> key=value:NoSchedule` | Add a node taint |
| `kubectl get nodes -o jsonpath='{.items[*].status.addresses}'` | Extract node IPs |

---

## Output Formatting
| Command | Description |
|---------|-------------|
| `kubectl get pods -o wide` | Show pods with extra details |
| `kubectl get pods -o json` | Output in JSON format |
| `kubectl get pods -o custom-columns=...` | Custom column output |

---

## Plugin Management (krew)
| Command | Description |
|---------|-------------|
| `kubectl krew install <plugin>` | Install a krew plugin |
| `kubectl krew upgrade` | Upgrade plugins |

---

## Utility Commands
| Command | Description |
|---------|-------------|
| `kubectl version --short` | Show brief version info |
| `kubectl wait --for=condition=Ready pod/<pod>` | Wait for pod readiness |

---

## Deprecated/Historical Commands
| Command | Description |
|---------|-------------|
| `kubectl run <name> --image=<image>` | Create a pod (deprecated) |

---

> **Notes**:  
> - Replace placeholders like `<pod-name>`, `<file.yaml>`, etc., with actual values.  
> - Use `-n <namespace>` for namespace-specific operations.  
> - Add `--all-namespaces` to target all namespaces.  
> - Combine with `watch` for real-time monitoring: `watch kubectl get pods`.  

For more details, refer to the [official Kubernetes documentation](https://kubernetes.io/docs/reference/kubectl/cheatsheet/).
