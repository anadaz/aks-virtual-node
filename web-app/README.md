## Build and run locally
```docker build -t <username>/static-web:latest .```

```docker run -itd --name static-web --publish 8080:80 <username>/static-web:latest```

## Login and publish to docker hub 
```docker login --username=<username> --email=<useremail>```

```docker push <username>/static-web:latest```