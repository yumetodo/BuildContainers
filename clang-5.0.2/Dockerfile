FROM alpine:3.9
RUN apk add --update clang=5.0.2-r0 gcc cmake=3.13.0-r0 git ruby perl make bash
RUN gem install lcoveralls
RUN git clone https://github.com/linux-test-project/lcov.git ./lcov -b v1.14 --depth 1 && cd lcov && make install
