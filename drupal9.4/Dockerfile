FROM docksal/cli:php8.0-3.2

# Install clamav
RUN apt-get --allow-releaseinfo-change update && \
    apt-get install -y clamav

# Update AV Database
RUN freshclam

# Install
# - ghostscript for PDF to image conversion
# - pngcrush for PNG compression
# - jpegtran for JPEG compression
# - python2 for node-fibers dependency.
# - automake for gifsicle dependency.
RUN apt-get --allow-releaseinfo-change update && \
    apt-get install -y ghostscript pngcrush libjpeg-progs python2 automake && \
    apt-get install -y dh-autoreconf

RUN alias python=/usr/bin/python2

# Install kafka.
RUN rm -rf /librdkafka \
    && git clone --depth 1 --branch v1.2.0 https://github.com/edenhill/librdkafka.git \
    && cd librdkafka \
    && ./configure \
    && make \
    && make install

RUN pecl install rdkafka-5.0.2
