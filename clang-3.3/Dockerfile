FROM alpine:3.9
RUN echo http://dl-cdn.alpinelinux.org/alpine/v2.7/main/ >> /etc/apk/repositories && \
        apk add --no-cache clang=3.3-r1 gcc g++ cmake=3.13.0-r0 git ruby ruby-rdoc perl make bash && \
        gem install lcoveralls && \
        git clone https://github.com/linux-test-project/lcov.git ./lcov -b v1.14 --depth 1 && cd lcov && make install && cd .. && rm -rf lcov
