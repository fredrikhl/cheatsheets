# mutt

## Patterns for search/limit

| Pattern          | Description                                          |
| ---------------- | ---------------------------------------------------- |
| `~A`             | all messages                                         |
| `~b PATTERN`     | `PATTERN` in the message body                        |
| `=b PATTERN`     | `PATTERN` in the message body, on IMAP server        |
| `~B PATTERN`     | `PATTERN` in the whole message                       |
| `=B PATTERN`     | `PATTERN` in the whole message, on IMAP server       |
| `~c PATTERN`     | `PATTERN` in the `Cc` header                         |
| `~C PATTERN`     | `PATTERN` in the `To` or `Cc` headers                |
| `~D`             | deleted messages                                     |
| `~d [MIN]-[MAX]` | `date-sent` in the given Date range                  |
| `~E`             | expired messages                                     |
| `~e PATTERN`     | `PATTERN` in the `Sender` field                      |
| `~F`             | flagged messages                                     |
| `~f PATTERN`     | `PATTERN` in the `From` header                       |
| `~h PATTERN`     | messages which contain PATTERN in the message header |
| `~i ID`          | `ID` matches the `Message-ID`                        |
| `~k`             | messages with PGP data (signed, etc... )             |
| `~L PATTERN`     | message is either originated or received by PATTERN  |
| `~l`             | message is addressed to a known mailing list         |
| `~m [MIN]-[MAX]` | message in the range MIN to MAX                      |
| `~n [MIN]-[MAX]` | messages with a score in the range MIN to MAX        |
| `~N`             | new messages                                         |
| `~O`             | old messages                                         |
| `~p`             | message is addressed to you (consults $alternates)   |
| `~P`             | message is from you (consults $alternates)           |
| `~Q`             | messages which have been replied to                  |
| `~R`             | read messages                                        |
| `~r [MIN]-[MAX]` | messages with 'date-received' in a Date range        |
| `~S`             | superseded messages                                  |
| `~s SUBJECT`     | messages having SUBJECT in the 'Subject' field.      |
| `~T`             | tagged messages                                      |
| `~t USER`        | messages addressed to USER                           |
| `~U`             | unread messages                                      |
| `~x PATTERN`     | `PATTERN` in the `References` field                  |
| `~z [MIN]-[MAX]` | messages with a size in the range MIN to MAX         |


## Ranges

### Absolute date

- Range: `DD[/MM[/YY]]-DD[/MM[/YY]]`
- Before: `-DD[/MM[/YY]]`
- After: `DD[/MM[/YY]]-`

### Relative date

- Older: `>[0-9]+[dwmy]`
- Newer: `<[0-9]+[dwmy]`
- Exatly: `=[0-9]+[dwmy]`


### Size
TODO

### Score
TODO


## Fields

- Sender: TODO
- References: TODO

