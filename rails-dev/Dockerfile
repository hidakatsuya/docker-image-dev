FROM ruby:3.2.0

# Install vim
RUN apt-get update && apt-get install -y --no-install-recommends vim &&\
  apt-get clean && rm -fr /var/lib/apt/lists/*

# turn off auto complete in rails console
RUN echo 'IRB.conf[:USE_AUTOCOMPLETE] = false' > ~/.irbrc

WORKDIR /app

# configure bundler
RUN bundle config set --local path /bundle
