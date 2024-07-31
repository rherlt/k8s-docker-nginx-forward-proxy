# Use as a Debug Proxy server in k8s
```sh
# install pod in k8s cluster
kubectl apply -f k8s-pod.yaml -n my-namespace
# set up port forwarding from local port 8085 (can be changed) to container port 80 (where the proxy is running)
kubectl port-forward pods/0-debug-forward-proxy 8085:80 -n my-namespace
```

# Use as a debug Proxy server docker
```sh
# run in docker and setup port forwarding
docker run -it -p 8085:80 ghcr.io/rherlt/docker-nginx-forward-proxy:main
```

# ⚠️ Do not forget ⚠️
Set up proxy server settings the application you want to test. Use localhost (127.0.0.1) and local port (e.g. 8085) for the settings.

# Special Thanks
Inspired by https://github.com/soulteary/docker-nginx-forward-proxy