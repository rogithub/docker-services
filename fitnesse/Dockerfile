FROM openjdk:8-jre-alpine
MAINTAINER Rodrigo Debian <correo.rodrigo@gmail.com>
RUN adduser -D -u 666 fitnesse
#FNREL is Version # got from http://fitnesse.org/FitNesseDownload
ENV FNREL=20190119
RUN mkdir -p /opt/fitnesse
RUN mkdir -p /tests
RUN wget -O "/opt/fitnesse/fitnesse-standalone.jar" "http://www.fitnesse.org/fitnesse-standalone.jar?responder=releaseDownload&release=$FNREL" && \
    chown fitnesse.fitnesse /opt/fitnesse
ADD start.sh /start.sh
RUN chmod o+x /start.sh
RUN chmod o+x /tests/NetRunner.Executable.exe
ENTRYPOINT ["/start.sh"]
