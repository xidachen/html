This repository hosts the [HTML Standard](https://html.spec.whatwg.org/).

### Pull requests

The short version is that all you need to do is change the `source` resource and submit a patch. The longer version is that you probably want to read the [WHATWG FAQ](https://wiki.whatwg.org/wiki/FAQ) first.

Please also add your name to the Acknowledgements section (search for `<!-- ACKS`) in your first pull request, even for simple typo fixes. The names are sorted alphabetically.

To preview your changes locally, follow the instructions in the [html-build repository](https://github.com/whatwg/html-build). Alternately, if you are familiar with Docker, see the instructions below for a potentially-easier route.

The source for the spec is formatted in such a way that its paragraphs have line breaks after about every 100 characters or so. Any patch you contribute must follow that same formatting convention. So, use whatever option your text editor may provide for automatically doing that kind of "hard" wrapping of lines at 100 characters; for example, in Emacs, set `fill-column` to `100`; in Vim, set `textwidth` to `100`; and in Sublime, set `wrap_width` to `100`.

Please follow the [guidelines for writing good commit messages](https://github.com/erlang/otp/wiki/Writing-good-commit-messages).

### Contribution opportunities

The HTML Standard is complex and people notice minor (and large) issues with it all the time. We'd love your help fixing these.

We've collected a list of good first bugs that you could help us fix, to get a taste for how to submit pull requests, how the build process works, and so on:

- [Legacy Bugzilla bugs](https://www.w3.org/Bugs/Public/buglist.cgi?bug_status=UNCONFIRMED&bug_status=NEW&bug_status=ASSIGNED&bug_status=REOPENED&component=HTML&list_id=59457&product=WHATWG&query_format=advanced&resolution=---&status_whiteboard=[good%20first%20bug]&status_whiteboard_type=allwordssubstr)
- [GitHub issues](https://github.com/whatwg/html/labels/good%20first%20bug)

We'd be happy to mentor you through this process. If you're interested and need help getting started, leave a comment on the bug or issue, or ask around [in IRC](https://wiki.whatwg.org/wiki/IRC).

### Building with Docker

If you know how to use [Docker](https://www.docker.com/), you may find the supplied Dockerfile an easier way to build than setting up the build environment locally per the [html-build repository](https://github.com/whatwg/html-build). Simply check out the repo, and run

```
docker build -t whatwg-html .
```

to build the standard. The first time will download a bunch of stuff and take a while to set up the environment, but subsequent runs will simply build the standard and will be fast. To view the built result, run

```
docker run --rm -it -p 8080:80 whatwg-html
```

which will allow you to view the result at `http://localhost:8080`. (OS X users will need to use the IP address of their docker-machine VM instead of `localhost`. You can get this with the `docker-machine env` command.)
