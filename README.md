# cronjobs

# To set up cronjobs
- crontab -l

it will output "no crontab for user" or it will show the cronjobs that exist

- crontab -e

if it is the first time, choose an editor and proceed.
Then start editing the crontab

# Commands

```sudo sh -c "du -ch /var/lib/docker/containers/*/*-json.log"

sudo sh -c "truncate -s 0 /var/lib/docker/containers/*/*-json.log"



docker image prune --all

docker system prune --all

docker volume prune --all
```
