# Evergreen Quote API: Phase 3 Capstone Starter

This is the engineering team's baseline for the Evergreen Quote API service.
It runs as-is, but it is deliberately not finished: the quote routes, the
GraphQL layer, the container recipe, the pipeline, and the cluster manifests
arrive as provided pieces during the week. You assemble onto this; you never
write code from scratch.

## Run it in a terminal
```bash
npm install
npm run dev
```

Then, in a second terminal:
```bash
curl http://localhost:3000/
```

## Preview the site
```
cd site
python3 -m http.server 8080
```

## Build the image
```
docker build -t evergreen-quote-api:1.0 .
```

## Run the API from the image
```
docker run --rm --network host --env-file .env evergreen-quote-api:1.0
```

## Deploy the image to a cluster
```
kind create cluster --name evergreen
docker pull mongo:7
kind load docker-image evergreen-quote-api:1.0 --name evergreen
kind load docker-image mongo:7 --name evergreen
kubectl apply --dry-run=client -f k8s/
kubectl apply -f k8s/mongo.yaml
kubectl wait --for=condition=available deploy/mongo --timeout=180s
kubectl apply -f k8s/
kubectl get pods
```

## Stop a cluster
```
kind delete cluster --name evergreen
```

## Make the image available to a Service
```
kubectl port-forward svc/evergreen-quote-api 8080:80
```