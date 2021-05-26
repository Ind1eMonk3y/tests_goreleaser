This repository is made just to try [goreleaser](https://github.com/goreleaser/goreleaser) and [godownloader](https://github.com/goreleaser/godownloader).

## Installation

Run this from your CLI to install this tool :

```bash
curl -o- -s https://raw.githubusercontent.com/Ind1eMonk3y/tests_goreleaser/main/install.sh | bash
```

You can also pass in a directory already on your PATH.

```bash
curl -o- -s https://raw.githubusercontent.com/Ind1eMonk3y/tests_goreleaser/main/install.sh | bash -s -- -b /usr/local/bin/
```

## Notes

### goreleaser

-  If you already have `Go` installed, install `goreleaser` by running this command or any of the commands listed [here](https://goreleaser.com/install/).

```bash
go install github.com/goreleaser/goreleaser
```

-  Inside your project working directory, generate the `goreleaser` configuration file by running this command.

```bash
goreleaser init
```

-  Customize the configuration for your needs and try it by running this command.

```bash
goreleaser --snapshot --skip-publish --rm-dist
```

-  Create the appropriate environment variable for the token

You could also paste the token in `~/.config/goreleaser/github_token`.

More informations can be found [here](https://goreleaser.com/quick-start/) or [here](https://goreleaser.com/environment/).

```bash
export GITHUB_TOKEN="YOUR_GH_TOKEN"
```


-  Add a tag and push your modifications

```bash
git tag -a v0.1.0 -m "First release"
git push origin v0.1.0
```

-  Make your release

```bash
goreleaser release --rm-dist
```


### godownloader

- If you already have `Go` installed, install `godownloader` by running this command or use any binaries from [here](https://github.com/goreleaser/godownloader/releases).

```bash
go get github.com/goreleaser/godownloader
cd "$GOPATH/pkg/mod/github.com/goreleaser/godownloader@v0.1.0"
go install .
```

- Go into your project working directory and run this command.

```bash
godownloader --repo=<user_name>/<project_name> > ./install.sh
```

