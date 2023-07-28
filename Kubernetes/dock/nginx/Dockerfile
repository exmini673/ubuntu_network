FROM nginx:1.25.1  
#nginx는 curl이 설치되어 있어서 기본 이미지만 사용
ENV REPO=static-web-template
ENV TAG_VERSION=1.3

RUN curl -LJO https://github.com/exmini673/${REPO}/archive/refs/tags/v${TAG_VERSION}.tar.gz
RUN tar -zxvf ${REPO}-${TAG_VERSION}.tar.gz
RUN mv ${REPO}-${TAG_VERSION}/htdocs/* /usr/share/nginx/html
RUN rm -rf ${REPO}-${TAG_VERSION}
RUN rm -rf ${REPO}-${TAG_VERSION}.tar.gz 