# Deploying our app

## Initial deploy

* On shell, `cd ~workshop/deploy/omniscient`.
* Setup environment `./setup.sh`
* Deploy application `./docker-compose.sh up -d`
* Review environment `./docker-compose.sh ps`

## Test our application

* `curl -X POST -d '{"content": "a new note"}'  159.203.33.226:8999/notes`
* `curl http://159.203.33.226:8999/notes`
* `curl http://159.203.33.226:8999/metrics`
* `curl http://159.203.33.226:8999/app/info`
* `curl http://159.203.33.226:8999/healthz`

## Repdeploying our application

* On shell, `cd ~workshop/deploy/omniscient`.
* Pull a new version of our application, `./docker-compose pull`
* Redeploy our application `./docker-compus up web`
