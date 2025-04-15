# Use a Ruby base image (adjust version if needed)
FROM ruby:3.2-bullseye

# Install necessary packages
RUN apt-get update && apt-get install -y \
    build-essential \
    nodejs \
    npm \
    git \
    && rm -rf /var/lib/apt/lists/*

# Install Jekyll and Bundler
RUN gem install jekyll bundler

# Set the working directory
WORKDIR /app

# Copy Gemfile and Gemfile.lock (if you have them)
COPY Gemfile Gemfile.lock ./

# Install gems
RUN bundle install

# Copy the Jekyll project files
COPY . ./

# Build the Jekyll site
CMD ["bundle", "exec", "jekyll", "build"]