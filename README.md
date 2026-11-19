# jbarciv.github.io

Personal academic website of Josep M. Barberá, built with Jekyll on the [al-folio](https://github.com/alshedivat/al-folio) theme and deployed to GitHub Pages via `.github/workflows/deploy.yml`.

## Local preview

The upstream `al-folio:latest` Docker image (Ruby 4) fails to build this site, so use Ruby 3.2 (same as the deploy workflow):

```bash
docker run -d --name jbarciv-preview -p 8080:8080 \
  -v "$PWD":/srv/jekyll -v jbarciv-gems:/usr/local/bundle -w /srv/jekyll ruby:3.2 \
  bash -c "bundle install && bundle exec jekyll serve --port=8080 --host=0.0.0.0 --force_polling"
```

Then open http://localhost:8080. Stop it with `docker rm -f jbarciv-preview`.
