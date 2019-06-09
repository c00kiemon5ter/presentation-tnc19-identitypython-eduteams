## IdentityPython & eduTEAMS

<small>Ivan Kanakarakis &mdash; SUNET</small>


notes:

- hello all
- it's a pleasure to be presenting here at TNC19
- thanks to everyone involved
- the hard work put by both the organizers and the research communities
- that make this event possible every year

---

### @c00kiemon5ter

Technical lead for _eduTEAMS_

Architect for the _IdentityPython_ projects

Member of a team


notes:

- I am Ivan
- also known by the handle `c00kiemon5ter`
- well, because, I like cookies

- I am the technical lead for _eduTEAMS_
  - planning, design, code reviews and code contributions
- but, I also work for IdentityPython as the project architect
  - planning, design, code reviews and code contributions

- everything I do would not be possible
- without the help of so many people
- the teams behind IdentiyPython and eduTEAMS

- the speakers before me told you about eduTEAMS
- I am going to talk a bit about IdentityPython
- and the core components that support eduTEAMS

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
* pyOP / OIDCendpoint
* pyXMLSecurity
* SATOSA
* pyFF


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
  * (maybe skip)
  * high-level libraries, intended to be usable in any web server application
  * provide the core functionality for OpenID Connect
    * Authorization Code Flow
    * Implicit Flow
    * Hybrid Flow
    * Requesting Claims using Scope Values
    * Claims Request Parameter
    * Currently only supports issuing signed ID Tokens

- pyXMLSecurity
  - implements the XML-DSIG part of XML-Security
  - sign with PKCS#11

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

---

### IdentityPython and eduTEAMS
### are mutually supportive


notes:

- both pyff and particularly satosa
- which are the high-level components
- are used extensively by eduTEAMS

- through those, eduTEAMS makes use of most other
- lower-level components provided by IdentityPython

- satosa fulfils the role of the proxy component in the AARC BPA
- while, pyff is used as the MDS and DS component

- as eduTEAMS relies heavily on those components
- to be up and running, working as needed
- it is driven by the design choices of those projects
- and, at the same time, partially drives the needed features

- by supporting these components
- IdentityPython can now be used to bring into life the AARC BPA

---

### More than projects


notes:

- IdentityPython is open source
- and eduTEAMS will be publishing all components
- under a permissive open source license
- everyone can benefit

- IdentityPython strives in the small
- to create the federated identity stack in python
- a flexible, easy to write, easy to read, easy to use language

- in the big, it strives to create a community
- a community of identity management professionals
- it is open and invites everyone to participate and join this community

---

### Resources

* https://idpy.org
* https://github.com/IdentityPython
* https://dracc.commonsconservancy.org/0024/
* https://dracc.commonsconservancy.org/0025/
* discuss@idpy.org


notes:

- you can learn more on the website
- check the projects under the GitHub organization profile
- and connect using the mailing list
