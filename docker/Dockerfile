ARG from
FROM $from

USER root

COPY Gemfile /fluentd/

RUN apk add --no-cache --virtual .build-deps build-base ruby-dev gnupg \
    && fluent-gem install bundle \
    && bundle install --gemfile /fluentd/Gemfile \
    && apk del .build-deps build-base \
    && gem sources --clear-all \
    && rm -rf /tmp/* /var/tmp/* /usr/lib/ruby/gems/*/cache/*.gem

USER fluent

