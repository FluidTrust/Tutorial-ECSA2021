# Website of Palladio Tutorial for ECSA 2021

This website uses the [Minimal Mistakes Jekyll theme](https://github.com/mmistakes/minimal-mistakes). Build and deployment is done by Github automatically.

Local building is possible in multiple ways but using docker is one of the cleanest options:

`docker run --rm -it -v $PWD:/srv/jekyll/:Z -p 4000:4000 jekyll/builder:latest /bin/sh -c "chown jekyll:jekyll /srv/jekyll/Gemfile.lock && chown jekyll:jekyll _site && bundle install && bundle exec jekyll serve --host 0.0.0.0"`

Every change except a change of the `_config.yml` file results in a rebuild. The result is available on [localhost:4000](http://localhost:4000). 

