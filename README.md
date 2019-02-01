# remove existing container
$ sudo docker rm postgres

# start
$ sudo docker-compose up -d

# list
$ sudo docker ps

# stop
$ sudo docker stop postgres

## BACKUP COMMAND
$ sudo docker exec postgres pg_dump -U postgres cc > ccbackup

## RESTORE COMMAND
$ cat ccbackup | sudo docker exec -i postgres psql -U postgres cc

## ssh conection
$ ssh -L [PUERTO LOCAL]:localhost:[PUERTO REMOTO] [SERVIDOR REMOTO]

## copy remote to local (use -r Recursively copy entire directories)
$ scp user@your.server.example.com:/path/to/myFile /home/user/Desktop/

## copy local to remote
$ scp myFile user@your.server.example.com:/path/to/destination/
