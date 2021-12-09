# data-baguette-ghost-blog

Ghost with Alto theme / pictures in the docker.

## Build

```bash
    git clone https://github.com/TryGhost/Alto alto
    gcloud auth login
    gcloud config set project data-baguette
    docker build -t gcr.io/data-baguette/ghost .
    docker push gcr.io/data-baguette/ghost
    gcloud run deploy --image gcr.io/data-baguette/ghost --platform managed --max-instances=2 --min-instances=1
```

## Link Google Cloud SQL

Re-deploy the service with:

- Adding the SQL connection in the "connection" section on the GUI
- Setup these env var:

  - database__client=mysql
  - database__connection__user=USER
  - database__connection__password=PATH
  - database__connection__socketPath=/cloudsql/PROJECT:REGION:INSTANCE
  - database__connection__database=DBNAME
  - url=https://URL.domain
