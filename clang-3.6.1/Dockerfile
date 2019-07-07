FROM alpine:3.9
RUN echo http://dl-cdn.alpinelinux.org/alpine/v3.2/main/ >> /etc/apk/repositories && \
        apk add --no-cache clang=3.6.1-r2 gcc g++ cmake=3.13.0-r0 git ruby ruby-rdoc perl make bash && \
        gem install lcoveralls && \
        git clone https://github.com/linux-test-project/lcov.git ./lcov -b v1.14 --depth 1 && cd lcov && make install && cd .. && rm -rf lcov
