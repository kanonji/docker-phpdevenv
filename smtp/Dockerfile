FROM alpine:3.7

ENV VERSION 0.6.5
ENV HTTP_PORT 80
ENV SMTP_PORT 25

RUN apk --update add --no-cache ruby ruby-dev ruby-bigdecimal sqlite sqlite-dev build-base libstdc++ ca-certificates && \
gem install json --no-ri --no-rdoc && \
gem install mailcatcher -v $VERSION --no-ri --no-rdoc && \
apk del --purge ruby-dev build-base

EXPOSE $SMTP_PORT $HTTP_PORT

CMD mailcatcher -f --ip=0.0.0.0 --smtp-port=$SMTP_PORT --http-port=$HTTP_PORT
