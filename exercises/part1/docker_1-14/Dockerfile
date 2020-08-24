FROM ruby:2.6.0
# throw errors if Gemfile has been modified since Gemfile.lock
RUN bundle config --global frozen 1
RUN apt-get update -qq && apt-get install -y nodejs

WORKDIR /usr/src/app

COPY rails-example-project/Gem* ./
RUN bundle install

COPY rails-example-project .

RUN rails db:migrate

CMD ["rails", "s"]