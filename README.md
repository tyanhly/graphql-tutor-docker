# About

Docker center for graphql-tutor

# Setup

```
# Clone source codes
git clone git@github.com/tyanhly/graphql-tutor.git
cd graphql-tutor
git clone git@github.com/tyanhly/graphql-tutor-client.git
git clone git@github.com/tyanhly/graphql-tutor-server.git

# Run docker compose
docker-compose up -d

```


# Develop 

## SERVER
```
docker exec  -it  bash -c 'cd /app/server && yarn'
docker exec  -it  bash -c 'cd /app/server && npm start'
```
