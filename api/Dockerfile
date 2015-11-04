FROM ruby:2.2

RUN apt-get update -qq && apt-get install -y build-essential libpq-dev nodejs
RUN git clone git://github.com/rails/rails.git
RUN cd /rails && bundle

WORKDIR /api
# Cache Gemfile changes
ADD Gemfile /api/Gemfile
RUN bundle install

ADD . /api

EXPOSE 3000

CMD ["bundle", "exec", "bin/rails", "s", "-b", "0.0.0.0"]
