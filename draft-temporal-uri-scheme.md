---
docname: draft-temporal-uri-scheme-latest
title: Temporal URI scheme
docname: draft-temporal-uri-scheme-latest
date: {DATE}
category: info

ipr: trust200902
area: General
keyword:
 - temporal
 - scheme

stand_alone: yes
smart_quotes: no
pi: [toc, tocindent, sortrefs, symrefs, strict, compact, comments, inline]

author:
 -
    ins: J. Fuller
    name: James Fuller
    organization:
    city: Prague
    region:
    country: Czech Republic
    email: jim@webcomposite.com
    uri: https://jim.fuller.name/

normative:
  RFC2119:

informative:


--- abstract

This document registers the "dt" URI scheme, to unambiguously identify
a discrete point in time.

--- note_Note_to_Readers

*RFC EDITOR: please remove this section before publication*

The issues list for this draft can be found at
<https://github.com/xquery/temporal-uri-scheme>.

* [Editor's Copy](https://xquery.github.io/temporal-uri-scheme/#go.draft-todo-temporal-uri-scheme.html)
* [Datatracker Page](https://datatracker.ietf.org/doc/draft-todo-temporal-uri-scheme)

--- middle

# Introduction

This document defines the URI scheme "dt", which describes resources identified by date-time.

## Notational Conventions

The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT",
"SHOULD", "SHOULD NOT",
"RECOMMENDED", "NOT RECOMMENDED", "MAY", and "OPTIONAL" in this
document are to be interpreted as
described in BCP 14 {{!RFC2119}} {{!RFC8174}} when, and only when,
they appear in all capitals, as
shown here.

This document uses ABNF {{!RFC5234}}. It also uses the date-time rule
from {{!RFC3339}}.

# The "temporal" URI Scheme

The "temporal" URI scheme allows for the construction of a URI which represents a discrete point in time.

~~~ abnf
temporal-URI    = temporal-scheme ":" dt
temporal-scheme = "dt"
dt              = date-time
~~~

See {{RFC3339, Section 5.6.3}} for a definition of date-time.

For example, given the URI:

~~~ examples
dt:20221222T162813Z
~~~

Would represent a discrete point in time of "2022-12-22T16:28:13Z".

The following examples would also be valid URIs:

~~~ examples
dt:2022-12-22T16:28:13Z
dt:1985-04-12T23:20:50.52Z
~~~

This RFC intentionally provides no definition of how URI's might be
parsed or compared by applications using them. For example, it is possible
to define two URI's which refer to the exact same point in time and it is
left to consuming application (or some future specification) to define what
that might 'mean'.


# IANA Considerations

This document registers the following value in the "Uniform Resource
Identifier (URI) Schemes" registry:

{: vspace="0"}
Scheme name:
: dt

Status:
: provisional

Applications/protocols that use this scheme:
: none yet

Contact:
: iesg@iesg.org

Change Controller:
: IESG

References:
: (this document)


# Security Considerations

TBA
--- back

# Acknowledgements
{:numbered="false"}

The definition of date-time is from {{?RFC3339}}.
