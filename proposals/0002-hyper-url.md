Title: **HYP-0002: hyper:// URL**

Short Name: `0002-hyper-url`

Type: Standard

Status: Draft (as of 2020-05-13)

Github PR:

Authors: Paul Frazee


# Summary
[summary]: #summary

The Hypercore Protocol uses a URL format as follows:

```
'hyper://' hypercore-id [ '+' version-tag ] hier-path [ '?' query ] [ '#' fragment ]
```

These segments are defined as follows:

 - `hypercore-id` An identifier for the Hypercore. Currently a base16-encoded public-key.
 - `version-tag` A string identifying a location in the Hypercore log sequence. May be an integer or a 'tag' string which matches the following regex `/[a-z][a-z0-9\.-]*/` (case insensitive).
 - `hier-path` The hierarchical path to a resource within the Hypercore, as defined in [RFC 3986 section 3.3](https://tools.ietf.org/html/rfc3986#section-3.3).
 - `query` Non-hierarchical data, as defined in [RFC 3986 section 3.4](https://tools.ietf.org/html/rfc3986#section-3.4).
 - `fragment` An indirect reference to secondary resources, as defined in [RFC 3986 section 3.5](https://tools.ietf.org/html/rfc3986#section-3.5).

# Changelog
[changelog]: #changelog

- 2020-05-13: First complete draft submitted provisionally
