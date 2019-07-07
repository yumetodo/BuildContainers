FROM alpine:3.2
RUN echo http://dl-cdn.alpinelinux.org/alpine/v3.9/main/ >> /etc/apk/repositories && \
        echo http://dl-cdn.alpinelinux.org/alpine/v3.9/community/ >> /etc/apk/repositories && \
        apk add --no-cache gcc=4.9.2-r6 cmake=3.13.0-r0 git ruby ruby-rdoc perl make bash libc6-compat && \
        gem install lcoveralls && \
        git clone https://github.com/linux-test-project/lcov.git ./lcov -b v1.14 --depth 1 && cd lcov && make install && cd .. && rm -rf lcov
