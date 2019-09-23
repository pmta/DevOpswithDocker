FROM ruby:2.6.0

WORKDIR /

RUN apt-get update && apt-get install -y curl git
RUN curl -sL https://deb.nodesource.com/setup_10.x | bash 
RUN apt-get install -y nodejs
RUN node -v && npm -v

RUN git clone https://github.com/docker-hy/rails-example-project.git
WORKDIR /rails-example-project/ 

RUN gem install bundler
RUN bundle install

RUN rails db:migrate
CMD rails s
#RUN rails db:migrate RAILS_ENV=production
#RUN rake assets:precompile
# CMD RAILS_LOG_TO_STDOUT=true rails s -e production

EXPOSE 3000

