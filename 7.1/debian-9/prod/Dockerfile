
FROM bitnami/php-fpm:7.1.23-debian-9-r15 as development

FROM bitnami/minideb-runtimes:stretch-php
LABEL maintainer "Bitnami <containers@bitnami.com>"

COPY --from=development /opt/bitnami/common /opt/bitnami/common
COPY --from=development /opt/bitnami/php /opt/bitnami/php

ENV BITNAMI_APP_NAME="php-fpm" \
    BITNAMI_IMAGE_VERSION="7.1.23-debian-9-r15" \
    PATH="/opt/bitnami/php/bin:/opt/bitnami/php/sbin:/opt/bitnami/php/sbin:$PATH"

CMD [ "php-fpm", "-F", "--pid", "/opt/bitnami/php/tmp/php-fpm.pid", "-y", "/opt/bitnami/php/etc/php-fpm.conf" ]
