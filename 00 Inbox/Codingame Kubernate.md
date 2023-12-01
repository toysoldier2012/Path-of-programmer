
# QCM

### Affinity
Language knowledge (40 pts)

What would the Kubernetes scheduler do during pod scheduling if we create a deployment `web‑store` with the following affinity configuration?  
  

```yaml
podAntiAffinity:
  preferredDuringSchedulingIgnoredDuringExecution:
  - labelSelector:
      matchExpressions:
      - key: app
        operator: In
        values:
        - web-store
    topologyKey: "kubernetes.io/hostname"
podAffinity:
  requiredDuringSchedulingIgnoredDuringExecution:
  - labelSelector:
      matchExpressions:
      - key: app
        operator: In
        values:
        - store
    topologyKey: "kubernetes.io/hostname"
```

_Multiple answers expected._

- It will make sure that no two `web-store` pods are scheduled on the same node. If not enough nodes fulfill the criteria then the pod will not be scheduled.
- It will make sure that the `web-store` and `store` pods are always co-located. If not enough nodes fulfill the criteria then the pod will not be scheduled.
- It will try to schedule `web-store` pods on different nodes but if not enough nodes are available then it will schedule multiple pods on a same node.
- It will try to schedule the `web-store` and `store` pods on same nodes but if not enough nodes are available then it will schedule the pods on different nodes.

### Secrets
Language knowledge (40 pts)

What would be the expected behavior when we apply the below configuration?  
  

```yaml
apiVersion: v1
kind: Secret
metadata:
  name: db-credentials
type: Opaque
data:
  login: YWRtaW4=
  password: MWYyZDFlMmU2N2Rm
---
apiVersion: v1
kind: Pod
metadata:
  name: front
spec:
  containers:
  - name: front
    image: apache
    volumeMounts:
    - name: foo
      mountPath: "/etc/foo"
    - name: bar
      mountPath: "/etc/bar"
  volumes:
  - name: foo
    secret:
      secretName: db-credentials
      items:
      - key: login
        path: credentials/my-login
  - name: bar
    secret:
      secretName: db-credentials
```

- The `password` secret is stored only under `/etc/bar/password`
- The `login` secret is stored under `/etc/bar/login` and `/credentials/my-login`
- The `login` secret is stored under `/etc/bar/login` and `/etc/foo/credentials/my-login`
- The `login` secret is stored only under `/etc/bar/login` because the foo volume configuration is incorrect (missing password).
- The `password` secret is stored under `/etc/bar/password` and `/etc/foo/password`

### AWS-EBS volumes
Language knowledge (40 pts)

A developer is trying to create a Pod on Kubernetes with the following configuration but the pod is not being created due to volume configuration. What could be the **possible reasons** for this behavior?  
  
```yaml
apiVersion: v1
kind: Pod
metadata:
  name: test-ebs
spec:
  containers:
  - image: k8s.gcr.io/test-webserver
    name: test-container
    volumeMounts:
    - mountPath: /test-ebs
      name: test-volume
  volumes:
  - name: test-volume
    awsElasticBlockStore:
      volumeID: vol-123456789
      fsType: ext4​
```

- The volume configuration is wrong, the developer should do it with Persistent volumes.
- The developer didn't create the EBS volume beforehand.
- The EBS volume is located in an availability zone where no nodes are present.
- The `fsType` should be **block** instead of **ext4**_**.**_

### Service creation command
Language knowledge (20 pts)

Which commands could be used to create a **service** on Kubernetes?

- kubectl expose
- kubectl run
- kubectl service
- kubectl create service

### RestartPolicy
Language knowledge (20 pts)

Which of the following is **not** a valid **restart policy** for a pod?

- Always
- OnFailure
- Never
- OnUpdate

### Probe handler
Language knowledge (40 pts)

In Kubernetes, a probe is a diagnostic performed periodically by the kubelet on a container. To perform a diagnostic, the kubelet calls a handler implemented by the container.

Which of the following **handler implementations is not supported** by Kubernetes?

- ExecAction
- TCPSocketAction
- UDPSocketAction
- HTTPGetAction

### Kubernetes usage
Language knowledge (20 pts)

Which of the following statements **are correct** about Kubernetes and its usage?

- It provides load balancing functionnalities for your services
- It can only support stateless applications
- It also provides application-level services, such as data-processing frameworks and databases as built-in services
- It provides storage orchestration

### Ingress usage
Language knowledge (20 pts)

Which of the following Kubernetes resource can be used to do **host-based routing** to several applications running inside the cluster?

- `Ingress`
- `IngressController`
- `LoadBalancer` type `Service`
- It cannot be done, we can only do **path-based** routing

### DaemonSet update strategy
Language knowledge (40 pts)

Which of the following are **valid update strategies** for a Kubernetes `DaemonSet`?

- OnDelete
- RollingUpdate
- Parallel
- Canary

### Replace command
Language knowledge (40 pts)

Which of the following commands will **delete and re-create** a resource?

- kubectl apply
- kubectl edit
- kubectl patch
- kubectl replace

### Object fields
Language knowledge (20 pts)

Which of the following is **not a required field** while creating a Kubernetes object?

- apiVersion
- kind
- status
- spec

# Text

# Code
