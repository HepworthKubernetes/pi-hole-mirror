# pi-hole

## Setup
Generate the secret per usual:
```bash
kubectl apply -f k8s/namespace.yaml

SECRET=$(openssl rand -hex 32)

kubectl create secret generic pihole-secret -n pihole \
    --from-literal=WEBPASSWORD="${SECRET}"

# Apply the manifests
kubectl apply -k k8s .
```

Pi-hole manifests
