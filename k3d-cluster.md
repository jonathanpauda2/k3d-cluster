Commands to create a kubernetes cluster using k3d on your laptop quickly - steps are for Mac OSX. [k3d documentataion](https://k3d.io/v5.5.1/#quick-start)

1. Install `k3d` using brew - `brew install k3d`

2. Start a k3d cluster called `alloy-demo` with a master node and 2 worker nodes (agents) - `k3d cluster create alloy-demo --servers 1 --agents 2`

3. verify the nodes are created:

`kubectl get nodes`

<pre>NAME                      STATUS   ROLES                  AGE   VERSION
k3d-alloy-demo-agent-0    Ready    <none>                 34s   v1.30.4+k3s1
k3d-alloy-demo-agent-1    Ready    <none>                 34s   v1.30.4+k3s1
k3d-alloy-demo-server-0   Ready    control-plane,master   37s   v1.30.4+k3s1</pre>

4. to stop the k3d cluster (when started again the same cluster will come back up) - `k3d cluster stop alloy-demo`

5. to delete the cluster - `k3d cluster delete alloy-demo`