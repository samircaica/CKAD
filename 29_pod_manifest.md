## **1. Create a Pod from Nginx Image**

### **Syntax:  kubectl run [NAME-OF-POD] --image=[IMAGE=NAME]**

##### **Command:**

```bash
kubectl run nginx --image=nginx
```

## **2. Create a Pod and Expose a Port**

```bash
kubectl run nginx --image=nginx --port=80
```

## **3. Output the Manifest File**

```bash
kubectl run nginx --image=nginx --port=80 --dry-run=client -o yaml
```
```yaml
apiVersion: v1
kind: Pod
metadata:
  creationTimestamp: null
  labels:
    run: nginx
  name: nginx
spec:
  containers:
  - image: nginx
    name: nginx
    ports:
    - containerPort: 80
    resources: {}
  dnsPolicy: ClusterFirst
  restartPolicy: Always
status: {}
```

## **4. Delete PODS**
```bash
kubectl delete pod nginx

kubectl delete pod --all
``` 

## **5. Explain fields**
```bash
kubectl explain pod.spec.containers
```