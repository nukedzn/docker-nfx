FROM node:lts-slim

# make & g++
RUN apt-get update \
	&& apt-get install -y --no-install-recommends \
		make \
		g++ \
	&& rm -rf /var/lib/apt/lists/*

# python
RUN apt-get update \
	&& apt-get install -y --no-install-recommends \
		python \
	&& rm -rf /var/lib/apt/lists/*

# CSDK dependencies
RUN apt-get update \
	&& apt-get install -y --no-install-recommends \
		file \
		libncurses5 \
	&& rm -rf /var/lib/apt/lists/*


ADD 4.10.FC5DE-dist.tar.xz /
RUN ln -s /opt/informix-clientsdk* /opt/informix-clientsdk

ENV INFORMIXDIR "/opt/informix-clientsdk"
ENV PATH "/opt/node/bin:${INFORMIXDIR}/bin${PATH:+:${PATH}}"
ENV LD_LIBRARY_PATH "${INFORMIXDIR}/lib:${INFORMIXDIR}/lib/c++:${INFORMIXDIR}/lib/cli:${INFORMIXDIR}/lib/client/csm:${INFORMIXDIR}/lib/dmi:${INFORMIXDIR}/lib/esql"

