# geolabel.net

A website for the GEO Label and the GEO Label Service: []()

Content roughly based on

- https://web.archive.org/web/20181117162415/http://geolabel.net/
- https://web.archive.org/web/20161027231050/http://www.geolabel.net/demo.html

## Tech

See `Makefile` for commands to build and view the site locally with [Jekyll](https://jekyllrb.com/).
The design is based on [`minima-reboot`](https://github.com/aterenin/minima-reboot).
If you want to override a file from the `minima-reboot` template, run `bundle info minima-reboot` to see where the bundle files are and copy it into this project.

## Prerequisites

- `ruby` and `ruby-dev`
- gem `bundler`

## Preview and build

```
make preview
make build
```

## Deploy

The site is build by GitHub, see https://jekyllrb.com/docs/github-pages/.

