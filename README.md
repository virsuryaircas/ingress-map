<p align="center">
  <img src="https://github.com/virsuryaircas/ingress-map/blob/main/imap-github-cover.svg?raw=true"
       alt="Ingress Map GitHub Cover"
       style="width: 500px; height: auto;" />
</p>

# 🗺️ Map to get location of all Hosts & Services

> An utility tool with dashboard built to visualize all the Ingress objects and Service entries from your k8s cluster in one place. It simplifies the process of checking routing path, host mappings, service targets, and access URLs without digging through YAML or CLI outputs.

## 🚀 Use Cases

- 📊 **Audit and Security Checks**  
  Instantly verify which external endpoints are exposed to the internet and how they map internally.

- 🛠️ **Troubleshooting Routing Issues**  
  Identify broken links between Ingress hosts and Service backends with a single glance.

- 🧭 **Infrastructure Mapping**  
  Use the dashboard as a service discovery map — great for onboarding new devs or reviewing environments.

- 📋 **Reporting and Documentation**  
  Screenshot or export the list of ingress routes and services for compliance or deployment documentation.

## 🧩 Advantages

- ⚡ Fast, no need to `kubectl get ingress` repeatedly
- 📦 Easy to deploy in any Kubernetes cluster
- 🔒 Useful for security audits — spot exposed hosts instantly
- 🧑‍💻 Developer-friendly UI – zero YAML reading needed
- 🔍 Great for large-scale clusters with multiple teams and namespaces

## 🛡️ Security

- Read-only access to Ingress and Service resources.
- Does not modify or mutate any cluster objects.

## ⚙️ Setup Instructions
 
```bash
# Clone the repository
git clone https://github.com/virsuryaircas/ingress-map.git

# To integrate Slack
cd ingress-map

# Apply the all manifests
kubectl apply -k .

# Verify the pod is in running state
kubectl get po -n podpulse

# Get your machine IP and copy it
hostname -I

# Note the NodePort
k get svc -n ingress-map
NAME                   TYPE        CLUSTER-IP      EXTERNAL-IP   PORT(S)        AGE
ingress-map-nodeport   NodePort    10.43.224.58    <none>        80:30050/TCP   5s
ingress-map-service    ClusterIP   10.43.121.201   <none>        80/TCP         5s

# Visit the Web UI
http://machineip:30050
```


### 📸 Screenshots

## 📝 Docker Image Changelog

**Docker Image**: [virsuryaircas/ingress-map](https://hub.docker.com/r/virsuryaircas/ingres-map)

### Version 1
- Initial release (inception)
