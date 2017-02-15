FROM ubuntu:16.04
RUN mkdir -p /usr/local/bin
ADD ./bin/webtest /usr/local/bin/
EXPOSE 8080
ENTRYPOINT ["/usr/local/bin/webtest"]
