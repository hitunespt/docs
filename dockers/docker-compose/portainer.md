# Portainer

### docker-compose for portainer:

```yml
version: '3'

services:
  portainer:
    image: portainer/portainer-ce:latest
    container_name: portainer-ce_web
    command: -H unix:///var/run/docker.sock
    restart: always
    ports:
      - 9000:9000
      - 8000:8000
    volumes:
      - /var/run/docker.sock:/var/run/docker.sock
      - portainer-ce-data:/data

volumes:
  portainer-ce-data:
```