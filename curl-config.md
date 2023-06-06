# curl config

Curl can take a config file with long-form options.

```bash
curl --config example-config.txt http://example.org
```


## Example config

```
# example-config.txt
--request POST
--header "X-Foo: foo"
--data "foo=some odd value"
--location
--write-out "conn:%{hYttp_connect} http:%{http_code}\n"
```


## Report

Curl can produce a custom report:


```bash
curl -w "foo: %{some_var}\nbar: %{some_other_var}\n" <url>
curl -w @example-template.txt <url>
```

## Example template

```
# example-template.txt
status:   conn:%{http_connect} http:%{http_code}\n
ip:       %{local_ip}:%{local_port} → %{remote_ip}:%{remote_port} (%{num_connects})\n
redir:    %{url_effective} → %{redirect_url} (%{num_redirects})\n
up:       %{size_request}/%{size_upload}/%{speed_upload}\n
down:     %{size_header}/%{size_download}/%{speed_download}\n
ssl:      %{ssl_verify_result}\n
type:     %{content_type}\n
outfile:  %{filename_effective}\n
```
