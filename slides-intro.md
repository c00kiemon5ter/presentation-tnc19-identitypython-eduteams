## IdentityPython & eduTEAMS

<small>Ivan Kanakarakis &mdash; SUNET</small>


notes:

- hello all
- it's a pleasure to be presenting here
- thanks to everyone involved
- the hard work put by both the organizers and the research communities
- that make this event possible every year

---

### @c00kiemon5ter

Architect for the _IdentityPython_ projects

Technical lead for _eduTEAMS_

Member of a team


notes:

- I am Ivan
- also known by the handle `c00kiemon5ter`
- well, because, I like cookies

- I work for SUNET on IdentityPython as the project architect
  - planning, design, code reviews and code contributions
- I am the technical lead for _eduTEAMS_
  - planning, design, code reviews and code contributions

- everything I do would not be possible
- without the help of so many people
- the teams behind IdentiyPython and the community

- I am going to talk a bit about IdentityPython

---

### What is IdentityPython?

https://idpy.org

![logo](images/identitypython.svg) <!-- .element: width="400" style="border: none; box-shadow: none;" -->


notes:

- so, what is IdentityPython?

- a set of projects related to identity management
- provide implementations of key federation and identity technologies
- such as: OpenID Connect, SAML, xmldsig, OAuth, JWT, and more

- all implemented in python
- all open source
- all under Apache 2.0 or BSD license

- started organizing & collecting the different projects since the mid of 2017
- today, under the umbrella of the Commons Conservancy foundation
- it is driven by a board committee
- it has a documented approach on
  - decision making
  - project inclusion and removal
  - and incident response processes
- you can learn more on the website

---

### Key-components

* pySAML2
* pyOP & OIDCendpoint
* pyXMLSecurity
* pyFF
* SATOSA


notes:

- let's have a quick look at the most important projects

- pysaml2
  - an implementation of the SAML2 specification
  - provides building blocks for SAML related constructs and concepts
  - but it goes beyond that
  - offers all necessary pieces for building complete SAML2 SPs or IdPs

- pyop / oidc-endpoint
  - it is for OIDC, what pysaml2 is for SAML
  - focus on providing everything needed to build an OP (OIDC Provider)
  - oidc-endpoint is a rewrite with a new architecture
    purpose of building a much simpler and more flexible library than pyop
  - (maybe skip)
  - high-level libraries, intended to be usable in any web server application
  - provide the core functionality for OpenID Connect
    - Authorization Code Flow
    - Implicit Flow
    - Hybrid Flow
    - Requesting Claims using Scope Values
    - Claims Request Parameter
    - Currently only supports issuing signed ID Tokens

- pyXMLSecurity
  - implements the XML-DSIG part of XML-Security
  - sign with PKCS#11

- pyFF
  - SAML metadata aggregator
  - based on the Metadata Interchange model by Ian Young
  - features
    - Pluggable "pipelines" for processing SAML metadata
    - Signature validation and creation
    - Support for using PKCS#11 tokens for signing
    - Certificate expiration, checking and reporting
    - Parallel fetching of multiple streams
    - Integrated discovery service
      - partially based on RA21.org P3W project
    - Support for eIDAS metadata service list format

- SATOSA
  - implements a proxy for translating between different authentication protocols
  - builds on top of pysaml2 and pyop
  - supports: SAML2, OpenID Connect and OAuth2
    - SAML2<->SAML2 / SAML2<->Social-logins / SAML2<->OIDC
  - tries to be very flexible and configurable
  - use cases:
    - Protocol conversion
    - Policy enforcement (InAcademia)
    - "Social" ID proxy (IdHub)
    - Make a non-conformant SP/IdP, SAML-compatible
    - Proxy an SP to many SAML IdPs and provide interface to IdP-discovery
    - Collaboration Management: Manage federated identities with
      customizing options, policies and custom attributes
    - Single point of trust
