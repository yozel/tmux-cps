# tmux-cps
Tmux Cluster Pod Shell

```
Usage: tmux-cps [options] [host ...]

Spawns multiple synchronized `kubectl exec [-n namespace] [-c contaier_name] [options] -it {pod_name} [shell]` sessions inside a tmux session.

Options:
  -h                     Show help
  -s <shell>             Shell process (default: bash)
  -n <namespace>         Kubernetes namespace
  -c <container>         Container name
  -l <label_selector>    Label selector (only effective if pod names are not given)
  -o <options>           Additional `kube exec` arguments
Examples:
  tmux-cps testapp-7987c95b6c-z5hq4 testapp-7987c95b6c-rn9l6
  tmux-cps -c nginx testapp-7987c95b6c-z5hq4 testapp-7987c95b6c-rn9l6
  tmux-cps -l release=testapp
  tmux-cps -l release=testapp -s sh
  tmux-cps -l release=testapp -n production
```
