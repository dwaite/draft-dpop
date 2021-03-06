# Introduction {#Introduction}

[@I-D.ietf-oauth-mtls] describes methods to bind (sender-constrain) access tokens
using mutual Transport Layer Security (TLS) authentication with X.509
certificates. 

[@I-D.ietf-oauth-token-binding] provides mechanisms to
sender-constrain access tokens using HTTP token binding.

Due to a sub-par user experience of TLS client authentication in user
agents and a lack of support for HTTP token binding, neither mechanism
can be used if an OAuth client is a Single Page Application (SPA)
running in a web browser.

This document defines an application-level sender-constraint mechanism for
OAuth 2.0 access tokens and refresh tokens that can be applied when neither mTLS nor
OAuth Token Binding are utilized. It achieves proof-of-possession using
a public/private key pair.


## Conventions and Terminology

The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL
NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED", "NOT RECOMMENDED",
"MAY", and "OPTIONAL" in this document are to be interpreted as
described in BCP 14 [@RFC2119] [@RFC8174] when, and only when, they
appear in all capitals, as shown here.


This specification uses the terms "access token", "refresh token",
"authorization server", "resource server", "authorization endpoint",
"authorization request", "authorization response", "token endpoint",
"grant type", "access token request", "access token response", and
"client" defined by The OAuth 2.0 Authorization Framework [@!RFC6749].
