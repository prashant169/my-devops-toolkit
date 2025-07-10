# my-devops-toolkit
# 💻 DevOps Daily Commands – Created from My Real-World Experience

These are the practical DevOps commands I use in my daily work — with comments explaining their real-world context. This cheat sheet spans:

✅ Linux System & Network  
✅ Docker & Kubernetes  
✅ Git & GitHub Actions (CI/CD)  
✅ AWS CLI  
✅ SSH, Logs, Permissions, and more

---

## 🖥️ Linux System & Network

```bash
df -h                        # Shows disk space usage (human-readable)
free -m                     # Displays free memory in MB (monitor RAM usage)
top                         # Live system resource usage (CPU, Memory, etc.)
htop                        # Enhanced top (if installed) for better view
ps aux | grep nginx         # Search running processes (e.g., nginx service)
netstat -tuln               # Show all listening ports (deprecated, but common)
ss -tuln                    # Preferred modern alternative to netstat
ping google.com             # Check basic network connectivity to external host
traceroute google.com       # Trace the network route/hops to a server
ip a                        # List IP addresses on your system
hostname -I                 # Quick way to show IP address only
```

---

## 🗃️ Logs & File Management

```bash
tail -f /var/log/syslog              # Live stream system logs in real-time
grep "ERROR" /var/log/app.log        # Search for the keyword "ERROR" in logs
du -sh * | sort -h                   # Show folder sizes & sort smallest to largest
find / -name "*.log"                 # Recursively find all `.log` files from root
tar -czvf logs.tar.gz /var/log/     # Archive (compress) a logs folder for backup or sharing
```

---

## 🐳 Docker (Containerization)

```bash
docker ps -a                         # List all containers (including stopped ones)
docker images                        # List all Docker images on your system
docker build -t myapp .              # Build Docker image from Dockerfile in current dir
docker run -d -p 8080:80 myapp       # Run container in background, expose it on port 8080
docker exec -it <container> bash     # Enter an interactive shell inside the container
docker rm <id>                       # Remove a stopped container
docker rmi <image>                   # Delete a Docker image
```

---

## ☸️ Kubernetes (K8s)

```bash
kubectl config current-context        # Check which Kubernetes cluster you're operating in
kubectl cluster-info                  # Show basic info about the connected cluster
kubectl get pods                      # List all running pods
kubectl get svc                       # List all services (ClusterIP, NodePort, etc.)
kubectl get deployments               # View all deployed apps
kubectl logs <pod>                    # View logs from a pod (for debugging)
kubectl exec -it <pod> -- bash        # Access pod shell (if container has bash)
kubectl apply -f app.yaml             # Deploy resources using manifest (create/update)
kubectl delete -f app.yaml            # Delete resources defined in manifest
```

---

## 🔧 Git & GitHub Actions (CI/CD)

```bash
git status                            # Check current changes and staged files
git add .                             # Stage all modified/added files for commit
git commit -m "message"               # Save your changes locally with a message
git push origin main                  # Push commits to GitHub
git checkout -b feature-branch        # Create and switch to a new branch
git pull                              # Fetch latest changes from the remote branch
act -j build                          # Simulate GitHub Actions workflows locally (if using act)
```

---

## ☁️ AWS CLI (Cloud Management)

```bash
aws configure                         # Set AWS credentials and default region/output
aws ec2 describe-instances            # List all EC2 instances
aws s3 cp file.txt s3://my-bucket/    # Upload file to S3 bucket
aws ec2 start-instances --instance-ids i-xxx   # Start a specific EC2 instance
aws ec2 stop-instances --instance-ids i-xxx    # Stop a specific EC2 instance
```

---

## 🛠️ Useful DevOps Tools

```bash
curl -X GET https://api.example.com/status   # Test REST APIs
cat file.json | jq '.data.status'            # Parse and filter JSON using jq
yamllint config.yaml                         # Check YAML syntax (great for K8s/Ansible files)
python3 script.py                            # Run a Python script (for automation or validation)
```

---

## 🔐 SSH, Permissions & Secure File Transfer

```bash
chmod 755 script.sh                          # Make a script executable (owner can run)
chown user:group file.txt                    # Change file owner and group
ssh user@server-ip                           # Connect to a remote server over SSH
scp file.txt user@server:/path/              # Securely copy file to a remote server
```

---

## 📄 Final Thoughts

These are commands I personally use across infrastructure setup, deployment, cloud automation, debugging, and monitoring. Whether you're setting up CI/CD pipelines or troubleshooting production, this guide will save you time.

🧠 Feel free to fork this repo or share it with your team!

— *Prashant*
