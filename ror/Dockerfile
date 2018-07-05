FROM ruby:2.3-alpine

RUN 	apk update && \
	apk add nodejs \
	build-base libxml2-dev libxslt-dev \
	postgresql postgresql-dev \
	libcurl curl-dev \
	&& rm -rf /var/cache/apk/

COPY wait-for /bin/
RUN chmod +x /bin/wait-for

RUN mkdir /app
WORKDIR /app

COPY Gemfile* /app/

RUN gem install bundler --no-ri --no-rdoc
RUN bundle update

WORKDIR /app

CMD /bin/sh
