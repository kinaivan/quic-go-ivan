FROM ubuntu:16.04
#RUN echo "deb [trusted=yes] http://packages.net4sat.org/opensand xenial oldstable" | tee /etc/apt/sources.list.d/opensand.list
RUN rm /etc/apt/sources.list.d/opensand.list
RUN echo "deb [trusted=yes] https://raw.githubusercontent.com/CNES/net4sat-packages/master/jammy/ jammy stable" | tee /etc/apt/sources.list.d/net4sat.list
RUN apt-get update
RUN apt-get install -y netcat
RUN apt-get install -y iputils-ping
RUN apt-get install -y net-tools
RUN apt-get install -y iproute2
RUN apt-get install -y qupzilla ca-certificates
RUN apt-get install -y iperf3
RUN apt-get install -y python3
RUN apt-get install -y openvpn
RUN apt-get install -y wget
RUN update-ca-certificates
COPY client.ovpn /root/client.ovpn
COPY speedtest.py /tmp/speedtest.py
COPY launch_firefox.sh /tmp/launch_firefox.sh
RUN chmod +x /tmp/launch_firefox.sh
CMD exec tail -f /dev/null