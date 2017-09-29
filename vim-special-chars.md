# vim: insert special characters

## insert bytes / unicode code points

`^V` in insert mode (see `help i_^V`)

* decimal (000 <= nnn <= 255): `^Vnnn`
* octal (000 <= nnn <= 377): `^VOnnn` or `^Vonnn`
* hex (00 <= nn <= FF): `^VXnn` or `^Vxnn`
* hex bmp (0000 <= nnnn <= FFFF): `^Vunnnn`
* hex (00000000 <= nnnnnnnn <= 7FFFFFFF): `^VUnnnnnnnn`


## digraphs:

* [ <c-k> a : ] ä
* [ <c-k> - > ] →

`:help i_digraph` for input help.  `:digraphs` for list
