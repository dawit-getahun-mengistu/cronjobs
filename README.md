# cronjobs

# To set up cronjobs
``` crontab -l```

it will output "no crontab for user" or it will show the cronjobs that exist

``` crontab -e ```

if it is the first time, choose an editor and proceed.
Then start editing the crontab

# Commands

```
*/5 * * * * sudo sh -c "du -ch /var/lib/docker/containers/*/*-json.log"
*/5 * * * * sudo sh -c "truncate -s 0 /var/lib/docker/containers/*/*-json.log"
*/5 * * * * docker image prune --all
*/5 * * * * docker system prune --all
*/5 * * * * docker volume prune --all
```
append this after running `crontab -e`. `*/5` means it runs every 5 minutes. change the timing as needed. If you want to log the results of the jobs (if they have outputs) you can direct it to log to a text file as shown below.
```
* * * * * sudo sh -c "du -ch /var/lib/docker/containers/*/*-json.log" >> /home/username/first_log.txt
* * * * * sudo sh -c "truncate -s 0 /var/lib/docker/containers/*/*-json.log" >> /home/username/truncate_log.txt
* * * * * docker image prune --all >> home/username/prune_log.txt
...
```
when the files are created, `ls` command should be able to list the files. Use `cat textfile_name.txt` to see the content.

GREP command `cat /var/log/syslog | grep CRON` shows a log of all the jobs and their status by user 
