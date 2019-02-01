# add user to docker group
sudo usermod -a -G docker $USER

# remove existing container
$ docker rm postgres

# start
$ docker-compose up -d

# list
$ docker ps

# stop
$ docker stop postgres

## BACKUP COMMAND
$ docker exec postgres pg_dump -U postgres cc > ccbackup

## RESTORE COMMAND
$ cat ccbackup | docker exec -i postgres psql -U postgres cc

## ssh conection
$ ssh -L [PUERTO LOCAL]:localhost:[PUERTO REMOTO] [SERVIDOR REMOTO]

## copy remote to local (use -r Recursively copy entire directories)
$ scp user@your.server.example.com:/path/to/myFile /home/user/Desktop/

## copy local to remote
$ scp myFile user@your.server.example.com:/path/to/destination/
