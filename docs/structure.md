---
layout: default
title:  "Marpa's Architecture"

---

# Marpa's Architecture

|                               | Description                            | Language | Depends on |
| ---                           | ---                                    | ---      | ---        |
| [libmarpa](#libmarpa)         | Implemntation of the parsing algorithm | C        | None       |
| [Marpa::R2](#marpar2scanless) | High level interface for libmarpa      | Perl     | libmarpa   |
| [Kollos](#kollos)             | WIP high level interface for libmarpa  | C, Lua   | libmarpa   |

## libmarpa
The library that is the principal implementation of the Marpa parsing
algorithm. libmarpa is not a high level interface, it is intended as a base
upon which higher-level interfaces can be built. As such, it is not directly
usable by someone wanting to parse something.

### Links
- [API documentation](http://jeffreykegler.github.com/Marpa-web-site/libmarpa_api/stable/index.html)
  ([single page](http://jeffreykegler.github.com/Marpa-web-site/libmarpa_api/stable/api_one_page.html),
   [pdf](https://docs.google.com/file/d/0B9_mR_M2zOc4ZkpJN0RaaGlkckU/edit?usp=sharing))
- [Usage example]({{ site.baseurl }}docs/libmarpa/json.html)

## Marpa::R2::Scanless
The primary high-level interface for Marpa, it takes a grammar in BNF form and
uses it to parse things. It does tokenization and other nice things, so it is
readily usable by someone wanting something parsed.

### Links
 - [Documentation](http://search.cpan.org/~jkegl/Marpa-R2-2.098000/pod/Scanless.pod)
 - [DSL documentation](http://search.cpan.org/~jkegl/Marpa-R2-2.098000/pod/Scanless/DSL.pod)
 - [Tutorial](http://marpa-guide.github.io/)

## Kollos
A new high level interface for libmarpa using C and lua. Still in the planning
stages.

### Links
  - [Source code](https://github.com/jeffreykegler/kollos/)
