# date

## UTC and Timezones

```bash
date -u
TZ=UTC0 date
TZ=Europe/London date
```

## Locale and names

```bash
LC_TIME=en_US date '+a %A in %B (%c)'
LC_TIME=nb_NO date '+en %A i %B (%c)'
```

## Timestamps

```bash
# from timestamp
date -d @899085600

# to timestamp
date +%s
```

## Input time

```bash
date -d '1998-06-28 20:00 -0600'
date -d 'next friday' -I

# more examples
info date 'Date input formats'

# from file modification
date -r <filename>
```

## Output formatting

```bash
# custom format with '+'
date "+%Y %d/%m %H:%M"

# iso-8601
date -I
date -I{d,h,m,s,n}
date --iso-8601={date,hours,minutes,seconds,ns}
date '+%G-W%V-%u'

# rfc-3339
date --rfc-3339={date,seconds,ns}

# rfc-5322
date --rfc-email
```
