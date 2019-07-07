FROM alpine:2.6
RUN echo http://dl-cdn.alpinelinux.org/alpine/v3.9/main/ >> /etc/apk/repositories && \
        echo http://dl-cdn.alpinelinux.org/alpine/v3.9/community/ >> /etc/apk/repositories && \
        apk add --update gcc=4.7.3-r6 cmake=3.13.0-r0 git ruby ruby-rdoc perl make bash && rm -rf /var/cache/apk/* && \
# This is a workaround to avoid the error shown below:
# cannot load such file -- rubygems/resolver/molinillo/lib/molinillo/dependency_graph/add_edge_no_circular (LoadError)
        ln -s /usr/lib/ruby/2.5.0/rubygems/resolver/molinillo/lib/molinillo/dependency_graph/add_edge_no_circular.r /usr/lib/ruby/2.5.0/rubygems/resolver/molinillo/lib/molinillo/dependency_graph/add_edge_no_circular.rb && \
        gem install lcoveralls && \
        git clone https://github.com/linux-test-project/lcov.git ./lcov -b v1.14 --depth 1 && cd lcov && make install && cd .. && rm -rf lcov
