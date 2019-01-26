FROM openjdk:8-jre-alpine
MAINTAINER Rodrigo Debian <correo.rodrigo@gmail.com>
RUN adduser -D -u 666 fitnesse
#FNREL is Version # got from http://fitnesse.org/FitNesseDownload
ENV FNREL=20190119
RUN mkdir -p /opt/fitnesse/hellotest
RUN wget -O "/opt/fitnesse/fitnesse-standalone.jar" "http://www.fitnesse.org/fitnesse-standalone.jar?responder=releaseDownload&release=$FNREL" && \
    chown fitnesse.fitnesse /opt/fitnesse
ADD start.sh /start.sh
ADD hellotest/fit.dll /opt/fitnesse/hellotest/fit.dll
ADD hellotest/Ro.Fitnesse.Library.dll /opt/fitnesse/hellotest/Ro.Fitnesse.Library.dll
ADD hellotest/NetRunner.Executable.exe /opt/fitnesse/hellotest/NetRunner.Executable.exe
RUN chmod o+x /start.sh
ENTRYPOINT ["/start.sh"]
