# wget

## examples

```bash
# To download a single file
wget http://example.org/file

# To download a file and change its name
wget http://example.org/file -O newname

# To download a file into a directory
wget -P path/to/directory http://example.org/file

# To continue an aborted downloaded
wget -c http://example.org/file

# To download multiples files with multiple URLs
wget URL1 URL2

# To parse a file that contains a list of URLs to fetch each one
wget -i url_list.txt

# To mirror a whole page locally
wget -pk http://example.org/page.html

# To mirror a whole site locally
wget -mk http://example.org/

# To download files according to a pattern
wget http://example.org/files-{1..15}.tar.bz2

# To download all the files in a directory with a specific extension if directory indexing is enabled
wget -r -l1 -A.extension http://example.org/directory

# Allows you to download just the headers of responses (-S --spider) and display them on Stdout (-O -).
wget -S --spider -O - http://example.org

# Change the User-Agent to 'User-Agent: my-agent'
wget -U 'my-agent' http://example.org
```
