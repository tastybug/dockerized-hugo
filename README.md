# Dockerized Hugo

`docker run --rm -ti "tastybug/dockerized-hugo" hugo version`

New site:
`cd my-site-repo && docker run --rm -v $PWD:/site "tastybug/dockerized-hugo" hugo new site /site`

Build site
`cd my-site-repo && docker run --rm -v $PWD:/site "tastybug/dockerized-hugo" hugo -s /site`

## Working on the site

Create a docker-compose file in the site (content) repository:

```
version: '3'

services:
  hugo:
    image: tastybug/dockerized-hugo:latest
    working_dir: /site
    volumes:
      - .:/site
    command: "hugo server --bind 0.0.0.0 --templateMetrics"
    ports:
      - 1313:1313
```

Then run it from within the site directory: `docker-compose up`

