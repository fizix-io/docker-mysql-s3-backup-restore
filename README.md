alpine + mysql-client + awscli + backup & restore script

## Backup

```sh
docker run --rm \
 --link mysql_container:mysql \
 -e AWS_ACCESS_KEY_ID=XXX \
 -e AWS_SECRET_ACCESS_KEY=XXX \
 -e S3_BUCKET=XXX \
 -e MYSQL_USER=XXX \
 -e MYSQL_PASSWORD=XXX \
 -e MYSQL_HOST=mysql \
 -e BASE_PATH=my_custom_path/my_custom_basename \
fizix/mysql-s3-backup-restore  \
/backup
```

## Restore

```sh
docker run --rm \
 --link mysql_container:mysql \
 -e AWS_ACCESS_KEY_ID=XXX \
 -e AWS_SECRET_ACCESS_KEY=XXX \
 -e S3_BUCKET=XXX \
 -e MYSQL_USER=XXX \
 -e MYSQL_PASSWORD=XXX \
 -e MYSQL_HOST=mysql \
 -e BASE_PATH=my_custom_path/my_custom_basename \
fizix/mysql-s3-backup-restore  \
/restore
```
