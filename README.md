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

## ssh conection
$ ssh -L [localP]:localhost:[remoteP] your.server.example.com

## copy remote to local (use -r Recursively copy entire directories)
$ scp user@your.server.example.com:/path/to/myFile /home/user/Desktop/

## copy local to remote
$ scp myFile user@your.server.example.com:/path/to/destination/
