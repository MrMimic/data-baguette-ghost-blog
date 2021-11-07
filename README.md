# data-baguette-ghost-blog

Ghost with Alto theme / pictures in the docker.

## Build

```bash
    git clone https://github.com/TryGhost/Alto alto
    gcloud auth login
    gcloud config set project data-baguette
    docker build -t gcr.io/data-baguette/ghost .
    docker push gcr.io/data-baguette/ghost
    gcloud run deploy --image gcr.io/data-baguette/home --platform managed --max-instances=2 --min-instances=1
```

