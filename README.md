# Dockerized Hugo

`docker run --rm -ti "tastybug/dockerized-hugo" hugo version`

New site:
`cd my-site-repo && docker run --rm -v $PWD:/site "tastybug/dockerized-hugo" hugo new site /site`

Build site
`cd my-site-repo && docker run --rm -v $PWD:/site "tastybug/dockerized-hugo" hugo -s /site`

