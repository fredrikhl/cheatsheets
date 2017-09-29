# samlsign

## NAME

samlsign - sign and verify XML documents


## SYNOPSIS

`samlsign <options>`


## DESCRIPTION

samlsign signs or verifies signed XML documents. To sign a document, use -s. To
verify a document, omit -s. One of the -c, -R, or -T options are required when
verifying. Either -k or -R is required when signing.

By default, samlsign signs or verifies standard input. Pass -u or -f to retrieve
the document from a URL or file path. Signed documents are always printed to
standard output.


## OPTIONS

Options:

| Option        | Description
| ------------- | -----------
| `-u URL`      | The URL of the document to sign or verify.
| `-f PATH`     | The full path of the document to sign or verify.
| `-id ID`      | Rather than acting on the entire document, only act on the object with the specified ID. Only that object (with its new signature) will be printed to standard output.
| `-s`          | Sign, rather than the default action of verify.
| `-k KEY`      | Specifies the full path to the key to use for signing.
| `-c CERT`     | Specifies the full path to the certificate to use for verification.
| `-R RESOLVER` | Specifies a credential resolver to use for either signing or verification.
| `-T TRUST`    | Specifies the trust engine for TrustEngine-based verification.
| `-M METADATA` | Specifies the metadata for TrustEngine-based verification.
| `-i ISSUER`   | Specifies the issuer for verification.
| `-p PROT`     | Specifies the protocol for TrustEngine-based verification. This option allows specification of an arbitrary protocol by name, but more commonly one would use one of the options listed below for standard protocol names.
| `-r RNAME`    | Specifies the resource name for TrustEngine-based verification. This option allows specification of an arbitrary resource name by name, but more commonly one would use one of the options listed below for standard resource names.
| `-ns RNS`     | Specifies the namespace for TrustEngine-based verification. If not given, the default is `SAML20MD_NS`.
| `-saml10`     | Use the SAML1.0 protocol for TrustEngine-based verification.
| `-saml11`     | use the SAML1.1 protocol for TrustEngine-based verification.
| `-saml2`      | use the SAML2.0 P NS protocol for TrustEngine-based verification.
| `-idp`        | Set the resouce name to IDPSSODescriptor for TrustEngine-based verification.
| `-aa`         | Set the resource name to AttributeAuthorityDescriptor for TrustEngine-based verification.
| `-pdp`        | Set the resource name to PDPDescriptor for TrustEngine-based verification.
| `-sp`         | Set the resource name to SPSSODescriptor for TrustEngine-based verification.


## EXIT STATUS

status | description
------:| -----------
     0 | Success.
    -1 | An error in how samlsign was called (incorrect arguments, for example).
    -2 | An error occurred when initializing the configuration.
   -10 | An exception was caught.


## EXAMPLES

To sign SAML 2.0 metadata, use:

```bash
samlsign -k /path/to/key -c /path/to/cert -f /path/to/metadata
```


## AUTHOR

This manpage were written by Ferenc Wágner and Russ Allbery for Debian
GNU/Linux.


## COPYRIGHT

Copyleft (C) 2008 Ferenc Wágner
This is free software in the public domain.
