FROM hiwill41/httpd:1.0
#httpd는 curl이 없기 때문에 curl을 만든 이미지를 사용한다
ENV REPO=static-web-template
ENV TAG_VERSION=1.1

RUN curl -LJO https://github.com/exmini673/${REPO}/archive/refs/tags/v${TAG_VERSION}.tar.gz
RUN tar -zxvf ${REPO}-${TAG_VERSION}.tar.gz
RUN mv ${REPO}-${TAG_VERSION}/htdocs/* /usr/local/apache2/htdocs


