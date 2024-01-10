FROM mogtofu33/drupal8ci:4.x-dev-10.1

RUN rm -rf /librdkafka \
    && git clone --depth 1 --branch v1.2.0 https://github.com/edenhill/librdkafka.git \
    && cd librdkafka \
    && ./configure \
    && make \
    && make install

RUN pecl install rdkafka-5.0.2
