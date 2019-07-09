FROM alpine:3.7

RUN apk add --update \
    curl \
    && rm -rf /var/cache/apk/*

RUN apk add --no-cache libedit
    
RUN mkdir -p /j && curl \
  http://www.jsoftware.com/download/j807/install/j807_linux64.tar.gz \
  > /j/j807_linux64.tar.gz && tar xvzf j/j807_linux64.tar.gz -C /j/

RUN ls j/j64-807/bin/
ADD ./entrypoint.sh /j/entrypoint.sh

EXPOSE 65001

ENTRYPOINT ["sh", "/j/entrypoint.sh"]
