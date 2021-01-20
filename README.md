# runvendor

DEPRECATED: See [gomodrun](https://github.com/dustinblackman/gomodrun) instead.

Slightly lazy shell script to build, cache, and execute binaries stored in your Golang projects vendor folder.

# Install

```
  curl -o /usr/local/bin/runvendor https://raw.githubusercontent.com/dustinblackman/runvendor/master/runvendor
  chmod +x /usr/local/bin/runvendor
```

# Usage

Add a constraint to `Gopkg.toml`, for example lets use Ginkgo.

```
  required = ["github.com/onsi/ginkgo/ginkgo"]
```

Then you can add the following to either a Makefile or `go generate` to run `ginkgo`. `runvendor` will generate a binary and keep it cached in your vendor folder.

```
  runvendor github.com/onsi/ginkgo/ginkgo -v -r .
```

If you commit your vendor folder, I'd recommend adding the .bin to your `.gitignore`.

```
  echo "vendor/.bin/" >> .gitignore
```
