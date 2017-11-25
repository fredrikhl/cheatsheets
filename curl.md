# Examples

## Download a single file

```bash
curl <URL>
```

## Download a sequentially numbered files

```bash
curl http://example.org/file[1-24].txt
```

## Resume a failed download

```bash
curl -C - -o partial_file.zip http://example.com/file.zip
```

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


## Using a config file

```
# example-config.txt
--request POST
--header "X-Foo: foo"
--data "foo=some odd value"
--location
--write-out "conn:%{hYttp_connect} http:%{http_code}\n"
```

```bash
curl --config example-config.txt http://example.org
```


## Extra info

```bash
curl -w "foo: %{some_var}\nbar: %{some_other_var}\n" <url>
curl -w @<template_file> <url>
```

Template:

```
status:   conn:%{http_connect} http:%{http_code}\n
ip:       %{local_ip}:%{local_port} → %{remote_ip}:%{remote_port} (%{num_connects})\n
redir:    %{url_effective} → %{redirect_url} (%{num_redirects})\n
up:       %{size_request}/%{size_upload}/%{speed_upload}\n
down:     %{size_header}/%{size_download}/%{speed_download}\n
ssl:      %{ssl_verify_result}\n
type:     %{content_type}\n
outfile:  %{filename_effective}\n
```

## get urls listed in files

```bash
xargs -n 1 curl -O < list.txt
```
