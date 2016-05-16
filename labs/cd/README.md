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

## Creating a new version of our application

* On shell, `cd ~`.
* Create development directory `mkdir development`
* Clone omniscient `git clone git@app.<project id>.y.pifft.com:omniscient.git`
* Check out work branch `git checkout add-delete`
* Check out master branch `git checkout master`
* Merge work branch `git merge add-delete`
* Push work to remote Git repository `git push origin master`
* Go to Jenkins, and create a new build

## Repdeploying our application

* On shell, `cd ~workshop/deploy/omniscient`.
* Pull a new version of our application, `./docker-compose pull`
* Redeploy our application `./docker-compus up web`
