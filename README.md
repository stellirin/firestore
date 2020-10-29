# Firestore Emulator

Easy emulation for local development on Kubernetes.

The `emulator` tag simply wraps the official Firestore emulator into a container.

## Firestore Emulator Deployment

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: firestore
  labels:
    app: firestore

spec:
  replicas: 1
  selector:
    matchLabels:
      app: firestore
  template:
    metadata:
      labels:
        app: firestore
    spec:
      containers:
      - name: firestore
        image: stellirin/firestore:emulator
        imagePullPolicy: Always
        ports:
          - name: firestore
            containerPort: 8080
```
