# curl

# Options

* -o <name>: Name the output file
* -O <remote>: Download <remote> and name it according to its remote name


## Auth

* -u <username>[:<password>]
* --key <file>: Use private (PEM) key in SSL/SSH request
* --key-type <(DER|PEM|ENG)>: Specify key format

## Net

* -x <host>:<port>: Add a proxy
* --limit-rate <num>B: Limit download rate to <num> bytes/sec


## HTTP

* -I: Only fetch headers
* -i: Include headers in output
* -H <header>: Add header to request, e.g. `curl -H "Foo: bar"`
* -L: Follow 3xx (relocate) responses
* -v: Verbose, shows request and response headers


## Security

* --cacert <file>: Specify CA-certificate (PEM) file
* --cert-type <(DER|PEM|ENG)>: Specify cacert format
* -k: Insecure SSL connection (ignore certificate validation failure)


## Proxy

Use a proxy for a given domain -- e.g. to force traffic through `ssltap`, but
let curl set SNI and Host-header.

```bash
ssltap -s -p 8443 example.org:443
curl https://example.org/ --connect-to example.org:443:localhost:8443
```


## Progress options

- `--no-progress-meter` - disables progress meter
- `-#`/`--progress-bar` - replaces meter with a simple progress bar
- `-s`/`--silent` - disables progress meter and other non-response output
- `-v`/`--verbose` - disables progress meter


## Examples

```bash
# Fetch urls listed in file
xargs -n 1 curl -O < list.txt

# download sequentially numbered files
curl http://example.org/file[1-24].txt

# resume a failed download
curl -C - -o partial_file.zip http://example.com/file.zip
```
