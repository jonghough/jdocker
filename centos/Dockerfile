FROM centos:7

RUN yum install -y curl libedit

RUN mkdir -p /j && curl \
  http://www.jsoftware.com/download/j807/install/j807_linux64.tar.gz \
  > /j/j807_linux64.tar.gz && tar xvzf j/j807_linux64.tar.gz -C /j/

RUN ls j/j64-807/bin/
ADD ./entrypoint.sh /j/entrypoint.sh

RUN cp /usr/lib64/libedit.so.0 /usr/lib64/libedit.so.2
EXPOSE 65001

ENTRYPOINT ["sh", "/j/entrypoint.sh"]
