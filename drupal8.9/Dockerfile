FROM mogtofu33/drupal8ci:8.9-drupal

RUN wget https://github.com/edenhill/librdkafka/archive/v1.3.0.tar.gz && \
    tar xvfz v1.3.0.tar.gz && \
    cd librdkafka-1.3.0 && \
    ./configure && \
    make && \
    make install && \
    pecl install rdkafka && \
    echo "extension=rdkafka" >> /usr/local/etc/php/php.ini && \
    cd .. && \
    rm -rf librdkafka-1.3.0
