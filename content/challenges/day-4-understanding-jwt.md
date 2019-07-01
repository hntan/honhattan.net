---
title: "Day Four - Understanding JSON Web Token(JWT)"
date: 2019-05-28T16:40:42+07:00
draft: true
---

## What is JSON Web Token

JSON Web Token as known as JWT, is a means of transmitting information between two parties in a compact, verifiable form.

JWT can be signed using a secret (with HMAC algorithm) or a public/private key pair using RSA or ECDSA.

## When to use it


## What is data structrure inside it.

In a compact form, a JWT contains three parts, separated by dot ( . ). which are:
* Header
* Payload
* Signature


## How does it work.

In authentication, when a use login successfully into an application, a JWT is returned to the client. So when a use need to access a resource, the agent should send JWT to the protected resource server, typically in the Authorization header via Bearer scheme.

`Authorization: Bearer <JWT>`


## Why to use it over other things.

* Lighweight
* Mobile App