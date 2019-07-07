FROM alpine:3.6
RUN echo http://dl-cdn.alpinelinux.org/alpine/v3.9/main/ >> /etc/apk/repositories && \
        echo http://dl-cdn.alpinelinux.org/alpine/v3.9/community/ >> /etc/apk/repositories && \
        apk add --no-cache gcc=6.3.0-r4 cmake=3.13.0-r0 git ruby ruby-rdoc perl make bash ca-certificates wget \
        linux-headers build-base openssl-dev libc-dev \
        libxml2-dev libxslt-dev libffi-dev readline-dev jemalloc-dev readline-dev && \
#       wget -O ruby-install-0.7.0.tar.gz https://github.com/postmodern/ruby-install/archive/v0.7.0.tar.gz && \
#       tar -xzvf ruby-install-0.7.0.tar.gz && \
# workaround: see https://github.com/postmodern/ruby-install/pull/348
        git clone https://github.com/yumetodo/ruby-install.git -b fix/uninstall --depth 1 && \
        cd ruby-install/ && \
        make install && \
        ruby-install --system ruby 2.6.3 && \
        cd /ruby-install/ && \
        make uninstall && \
        cd / && \
        rm -rf ruby-install && \
        apk del linux-headers build-base openssl-dev libc-dev libxml2-dev libxslt-dev libffi-dev jemalloc-dev && \
        echo "gem: --no-document" > ~/.gemrc && \
        gem install lcoveralls && \
        git clone https://github.com/linux-test-project/lcov.git ./lcov -b v1.14 --depth 1 && cd lcov && make install && cd .. && rm -rf lcov
