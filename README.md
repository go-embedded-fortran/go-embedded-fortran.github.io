# go-embedded-fortran.github.io

The go-embedded-fortran landing page (Hugo), served at <https://go-embedded-fortran.github.io/>.
The documentation is at <https://go-embedded-fortran.github.io/docs/> (repository
[go-embedded-fortran/docs](https://github.com/go-embedded-fortran/docs)).

The organization is **in development**. Every figure on the page is copied from the
README of `go-embedded-fortran/fortran` at v0.17.0: the evaluator runs all 14 golden
programs byte-identical to gfortran 15.2.0 and, since v0.17.0, a notebook's cells one
after the other (`eval.Session`, linked by go-notebook v0.17.0), the I/O runtime is identical to it on
71 096 of 71 135 differential cases (39 in documented classes), and the gate's first
figures give the verdict "A first". The page states the open defects: loop speed 8x to
108x behind gfortran -O2 (#17) and the gate's browser lane (#5). Its plan is the
roadmap's bibliography, `bib/fortran.md` in
[go-scikit/roadmap](https://github.com/go-scikit/roadmap).

The layout is the go-* family template: `layouts/index.html` and the shared
design (stylesheet, theme toggle, fork ribbon, icons), imported as the Hugo module
`github.com/go-fleettools/landingkit` pinned in `go.mod`. `[params.brand]`
in `hugo.toml` is read from the logo's gradient:

```sh
go run github.com/go-fleettools/landingkit/cmd/landingkit brand static/img/logo.svg
hugo server
```

| Workflow | What |
| --- | --- |
| `hugo.yml` | builds on pull requests; builds and deploys to Pages on `main` |
| `ci.yml` | the site builds and names every repository; `go mod tidy` keeps the landingkit requirement |
| `links.yml` | every link and image of the built site resolves |

BSD-3-Clause.
