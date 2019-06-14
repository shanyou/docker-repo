FROM centos:7.6.1810
LABEL maintainer = "Shan You <shanyou@gmail.com>"
LABEL Vendor="yunlu"

RUN yum install gcc make wget -y
RUN cd /opt \
&& wget http://www.thekelleys.org.uk/dnsmasq/dnsmasq-2.80.tar.gz \
&& tar xzvf dnsmasq-2.80.tar.gz \
&& cd dnsmasq-2.80 \
&& make \
&& make install

EXPOSE 53 53/udp
copy dnsmasq.conf /etc/dnsmasq.conf
RUN mkdir /etc/dnsmasq.d \
&& touch /etc/dnsmasq.hosts
ENTRYPOINT ["dnsmasq", "-k", "-d"]