FROM eclipse-temurin:21-alpine
# VocBench3
ARG VB_VERSION=14.0.0
# Semantic Turquey
ARG ST_VERSION=14.0
ARG ST_PATH=""

ENV ST_PATH=${ST_PATH} \
    VB_VERSION=${VB_VERSION} \
    ST_VERSION=${ST_VERSION}

# Install VocBench3 and Semantic Turquey
ADD https://bitbucket.org/art-uniroma2/vocbench3/downloads/vocbench3-${VB_VERSION}-full.zip /tmp

RUN set -eux ; \
	mkdir /opt/vocbench3 ; \
	mkdir /opt/vocbench3/data ; \
	cd /opt/vocbench3 ; \
	unzip -q /tmp/vocbench3-${VB_VERSION}-full.zip -d . ; \
	if [ -n "$ST_PATH" ]; then \
    mkdir -p /tmp/zipdiff/public/vocbench3/ && \
    unzip -p "semanticturkey-${ST_VERSION}/lib/vocbench3-${VB_VERSION}.jar" "public/vocbench3/vbconfig.js" > /tmp/zipdiff/public/vocbench3/vbconfig.js && \
    sed -i "s#^var st_path;#var st_path=\"${ST_PATH}\"#" /tmp/zipdiff/public/vocbench3/vbconfig.js && \
    jar -uf "semanticturkey-${ST_VERSION}/lib/vocbench3-${VB_VERSION}.jar" -C "/tmp/zipdiff" "public/vocbench3/vbconfig.js" && \
    rm -r /tmp/zipdiff ; \
	fi; \
  echo "ST_PATH: ${ST_PATH}" ; \
  echo "VB_VERSION: ${VB_VERSION}" ; \
  echo "ST_VERSION: ${ST_VERSION}" ; \
  mv "semanticturkey-${ST_VERSION}" semanticturkey ; \

RUN	cd /opt/vocbench3 && \
  chmod -R u=rwX,go=rX semanticturkey ; \
	chmod +x semanticturkey/bin/* ; \
	echo 'semanticturkey.data.dir=../data/SemanticTurkeyData' > semanticturkey/application.properties ; \
	rm /tmp/vocbench3-${VB_VERSION}-full.zip ; 

WORKDIR /opt/vocbench3/semanticturkey

EXPOSE 1979

ENTRYPOINT ["bin/semanticturkey.sh"]