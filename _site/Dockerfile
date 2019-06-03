FROM ruby:2.5
RUN apt-get update -qq && apt-get install -y nodejs && apt-get install -y git
RUN curl https://cli-assets.heroku.com/install.sh | sh
#RUN apt-get install zsh
#RUN sh -c "$(wget https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh -O -)"
RUN mkdir /myapp
WORKDIR /myapp
COPY Gemfile /myapp/Gemfile
COPY Gemfile.lock /myapp/Gemfile.lock
RUN bundle install
COPY . /myapp
EXPOSE 4000

# Start the main process.
CMD ["bundle", "exec", "jekyll", "s", "--incremental", "--host=0.0.0.0"]
