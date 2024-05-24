FROM pavja2/qpep:satellite
#RUN echo "deb [trusted=yes] http://packages.net4sat.org/opensand xenial stable" | tee /etc/apt/sources.list.d/opensand.list
RUN rm /etc/apt/sources.list.d/opensand.list
RUN apt-get update && \
    apt-get install -y apt-transport-https && \
    apt-get clean
RUN echo "deb [trusted=yes] https://raw.githubusercontent.com/CNES/net4sat-packages/master/jammy/ jammy stable" | tee /etc/apt/sources.list.d/net4sat.list
#RUN apt-get update
#RUN apt-cache madison opensand
#RUN apt-get install -y opensand
#RUN apt-get install -y opensand-manager
#RUN apt-get install -y opensand-collector
#RUN DEBIAN_FRONTEND=noninteractive apt-get -y install wireshark
#EXPOSE 3141
#EXPOSE 5358
#EXPOSE 5926
#RUN mkdir /root/.opensand
RUN apt-get update
RUN apt-get install -y xvfb
COPY config/sat.conf /etc/opensand/daemon.conf
COPY config/topology.conf /usr/share/opensand/topology.conf
#COPY config/core_global.conf /usr/share/opensand/core_global.conf
COPY config/entrypoint.sh /root/entrypoint.sh
RUN chmod +x /root/entrypoint.sh
ENTRYPOINT /bin/bash /root/entrypoint.sh
