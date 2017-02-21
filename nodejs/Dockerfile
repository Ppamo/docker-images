FROM ppamo.cl/devel:latest
MAINTAINER "Ppamo" <pablo@ppamo.cl>

# install nodejs by uncompresing file
COPY ["node-v6.9.5-linux-x64.tar.xz", "/opt/node-v6.9.5-linux-x64.tar.xz"]
RUN cd /opt && \
	tar xf /opt/node-v6.9.5-linux-x64.tar.xz && \
	ln -s node-v6.9.5-linux-x64 node && \
	echo "export PATH=$PATH:/opt/node/bin" >> /root/.bashrc && \
	echo "export PATH=$PATH:/opt/node/bin" >> /home/devel/.bashrc && \
	export PATH=$PATH:/opt/node/bin && \
	npm install -g http-server bower

# expose http-server port
EXPOSE 8080

# start sshd
CMD ["/usr/sbin/sshd", "-D"]
