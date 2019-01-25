build:	
	@echo "[deploying to docker]"
	sudo docker build -t "rofitnesse:latest" .
	sudo docker run --name rofitnesse -d -p:80:8080 rofitnesse:latest
	sudo docker stop rofitnesse
	sudo docker commit -m "adding rofitnesse" -a "Rodrigo Debian" rofitnesse rodocker/rofitnesse:latest
	sudo docker login
	sudo docker push rodocker/rofitnesse
	sudo docker rm rofitnesse
	sudo docker rmi rodocker/rofitnesse
	sudo docker rmi rofitnesse
