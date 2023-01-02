# Google PubSub Emulator Docker Image

Use the Google SDK image instead!

In `docker-compose.yml`

```yaml
services:
  pubsub: 
    image: google/cloud-sdk:emulators
    volumes:
      - pubsub-data:/opt/pubsub
    ports:
      - 8085:8085
    command: > 
      /google-cloud-sdk/bin/gcloud beta emulators 
      pubsub start 
        --data-dir /opt/pubsub
        --host-port "0.0.0.0:8085"
volumes:
  pubsub-data:
```

