FROM alpine:3.9
RUN apk add --no-cache gcc=8.3.0-r0 g++=8.3.0-r0 cmake=3.13.0-r0 git ruby ruby-rdoc perl make bash && \
        gem install lcoveralls && \
        git clone https://github.com/linux-test-project/lcov.git ./lcov -b v1.14 --depth 1 && cd lcov && make install && cd .. && rm -rf lcov
