FROM ruby:2.4.1

RUN gem update --system
RUN echo 'install: --no-document\nupdate: --no-document' >> "$HOME/.gemrc"
RUN gem install sigar -- --with-cppflags="-fgnu89-inline"
RUN gem install eye

# Installing packages
RUN apt-get update -qq
RUN apt-get install -y build-essential \
    apt-utils libxml2-dev libxslt1-dev \
    nginx imagemagick vim

# Installing NodeJS Latest LTS Version: v6.10.3
RUN curl -sL https://deb.nodesource.com/setup_6.x | bash -
RUN apt-get install -y nodejs

# Installing yarn
RUN curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | apt-key add -
RUN echo "deb https://dl.yarnpkg.com/debian/ stable main" | tee /etc/apt/sources.list.d/yarn.list
RUN apt-get update -qq
RUN apt-get install -y yarn
