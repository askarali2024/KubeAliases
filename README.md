# KubeAliases

**Kubernetes CLI shortcuts** — a curated set of shell aliases and helpers for `kubectl` to speed up daily cluster operations. Works with **bash** and **zsh**, and optionally uses [kubecolor](https://github.com/hidetatz/kubecolor) for colored output when installed.

---

## Features

- **Short aliases** — `kgp`, `kdp`, `klf` instead of long `kubectl` commands
- **Resource-focused** — pods, services, deployments, nodes, namespaces, and more
- **kubecolor support** — automatic use of `kubecolor` for `k get` / `k describe` when available
- **Portable** — single file, no extra dependencies except `kubectl`
- **Safe** — only aliases and small helpers; no destructive defaults

---

## Prerequisites

- **kubectl** — [Install guide](https://kubernetes.io/docs/tasks/tools/)
- **Bash** or **Zsh**
- *(Optional)* [kubecolor](https://github.com/hidetatz/kubecolor) — for colored `k get` / `k describe`

---

## Installation

1. **Clone the repository**

   ```bash
   git clone https://github.com/<your-username>/KubeAliases.git
   cd KubeAliases
   ```

2. **Source the aliases in your shell**

   **One-time (current session only):**

   ```bash
   source aliases/kaliases
   ```

   **Permanent** — add to `~/.bashrc` or `~/.zshrc`:

   ```bash
   if [[ -r ~/KubeAliases/aliases/kaliases ]]; then
       source ~/KubeAliases/aliases/kaliases
   fi
   ```

   Adjust the path if you cloned KubeAliases to a different directory.

3. **Reload your shell** (or open a new terminal)

   ```bash
   source ~/.zshrc   # or source ~/.bashrc
   ```

---

## Alias Reference

### Base

| Alias | Command | Description |
|-------|---------|-------------|
| `k` | `kubectl` | Main shortcut; uses kubecolor for `get`/`describe` when available |

### Context & config

| Alias | Command | Description |
|-------|---------|-------------|
| `kcfg` | `kubectl config` | Config subcommands |
| `kctx` | `kubectl config current-context` | Show current context |
| `kuse` | `kubectl config use-context` | Switch context |
| `kns` | `kubectl config set-context --current --namespace` | Set namespace for current context |

### Get resources

| Alias | Command | Description |
|-------|---------|-------------|
| `kg` | `kubectl get` | Get any resource |
| `kgp` | `kubectl get pods` | Pods (current ns) |
| `kgpw` | `kubectl get pods -o wide` | Pods (wide) |
| `kgpa` | `kubectl get pods -A` | Pods (all namespaces) |
| `kgpaw` | `kubectl get pods -A -o wide` | Pods (all ns, wide) |
| `kgs` | `kubectl get services` | Services |
| `kgd` | `kubectl get deployments` | Deployments |
| `kgrs` | `kubectl get replicasets` | ReplicaSets |
| `kgds` | `kubectl get daemonsets` | DaemonSets |
| `kgss` | `kubectl get statefulsets` | StatefulSets |
| `kgj` | `kubectl get jobs` | Jobs |
| `kgcj` | `kubectl get cronjobs` | CronJobs |
| `kgn` | `kubectl get nodes` | Nodes |
| `kgnw` | `kubectl get nodes -o wide` | Nodes (wide) |
| `kgns` | `kubectl get namespaces` | Namespaces |
| `kgcm` | `kubectl get configmaps` | ConfigMaps |
| `kgsec` | `kubectl get secrets` | Secrets |
| `kgpv` | `kubectl get pv` | PersistentVolumes |
| `kgpvc` | `kubectl get pvc` | PersistentVolumeClaims |
| `kging` | `kubectl get ingress` | Ingress |
| `kgnet` | `kubectl get networkpolicies` | NetworkPolicies |
| `kgall` | `kubectl get all` | All common resources |
| `kgallo` | `kubectl get all -o wide` | All (wide) |
| `kga` | `kubectl get all` | Same as `kgall` |
| `knodes` | `kubectl get nodes -o wide --sort-by=...` | Nodes (wide, sorted) |

### Describe

| Alias | Command | Description |
|-------|---------|-------------|
| `kd` | `kubectl describe` | Describe any resource |
| `kdp` | `kubectl describe pod` | Describe pod |
| `kds` | `kubectl describe service` | Describe service |
| `kdd` | `kubectl describe deployment` | Describe deployment |
| `kdn` | `kubectl describe node` | Describe node |
| `kdns` | `kubectl describe namespace` | Describe namespace |

### Logs

| Alias | Command | Description |
|-------|---------|-------------|
| `kl` | `kubectl logs` | Logs |
| `klf` | `kubectl logs -f` | Logs (follow) |
| `kl1h` | `kubectl logs --since=1h` | Logs (last 1h) |
| `kl1m` | `kubectl logs --since=1m` | Logs (last 1m) |
| `klp` | `kubectl logs -l` | Logs by label |

### Exec & attach

| Alias | Command | Description |
|-------|---------|-------------|
| `kx` | `kubectl exec -it` | Exec into pod (interactive) |
| `ka` | `kubectl attach -it` | Attach to pod |

### Apply, create, delete

| Alias | Command | Description |
|-------|---------|-------------|
| `kaf` | `kubectl apply -f` | Apply manifest file |
| `kdel` | `kubectl delete` | Delete resource |
| `kdelf` | `kubectl delete -f` | Delete from file |
| `krun` | `kubectl run` | Run a pod |

### Rollout & scale

| Alias | Command | Description |
|-------|---------|-------------|
| `kr` | `kubectl rollout` | Rollout subcommands |
| `krstatus` | `kubectl rollout status` | Rollout status |
| `krrestart` | `kubectl rollout restart` | Restart rollout |
| `krhistory` | `kubectl rollout history` | Rollout history |
| `krundo` | `kubectl rollout undo` | Rollback rollout |
| `kscale` | `kubectl scale` | Scale deployment/replicaset |

### Port-forward & proxy

| Alias | Command | Description |
|-------|---------|-------------|
| `kpf` | `kubectl port-forward` | Port-forward pod/svc |
| `kproxy` | `kubectl proxy` | API server proxy |

### Watch

| Alias | Command | Description |
|-------|---------|-------------|
| `kw` | `kubectl get -w` | Watch any resource |
| `kwp` | `kubectl get pods -w` | Watch pods |
| `kwn` | `kubectl get nodes -w` | Watch nodes |

### Edit & patch

| Alias | Command | Description |
|-------|---------|-------------|
| `ke` | `kubectl edit` | Edit resource |
| `kpatch` | `kubectl patch` | Patch resource |

### Copy & top

| Alias | Command | Description |
|-------|---------|-------------|
| `kcp` | `kubectl cp` | Copy to/from pod |
| `ktop` | `kubectl top` | Resource usage |
| `ktopn` | `kubectl top nodes` | Node usage |
| `ktopp` | `kubectl top pods` | Pod usage |

### Auth & debug

| Alias | Command | Description |
|-------|---------|-------------|
| `kauth` | `kubectl auth` | Auth subcommands |
| `kauthc` | `kubectl auth can-i` | Check permissions |
| `kdebug` | `kubectl run debug --rm -it ...` | Ephemeral debug pod (busybox) |

---

## Optional: kubecolor

For colored `kubectl get` and `kubectl describe` output, install [kubecolor](https://github.com/hidetatz/kubecolor). The `k` function will use it automatically when available; no extra config needed.

---

## Contributing

Contributions are welcome. Please open an issue or pull request for new aliases or improvements.

---

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.
