Create NGINX Pod: kubectl run --generator=run-pod/v1 nginx --image=nginx

Generate YAML, don't create pod: kubectl run --generator=run-pod/v1 nginx --image=nginx --dry-run -o yaml

Generate Deployment YAML file (-o yaml). Don't create it(--dry-run): kubectl create deployment --image=nginx nginx --dry-run -o yaml

Create a Service named redis-service of type ClusterIP to expose pod redis on port 6379: kubectl expose pod redis --port=6379 --name redis-service --dry-run=client -o yaml

Or

kubectl create service clusterip redis --tcp=6379:6379 --dry-run=client -o yaml

Create a Service named nginx of type NodePort to expose pod nginx's port 80 on port 30080 on the nodes: kubectl expose pod nginx --port=80 --name nginx-service --type=NodePort --dry-run=client -o yaml

Or

kubectl create service nodeport nginx --tcp=80:80 --node-port=30080 --dry-run=client -o yaml