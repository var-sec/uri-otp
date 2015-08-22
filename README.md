# URI based One-Time-Password

Revision: 0.1

## Abstract

This document describes a way to securely generate one-time-passwords (OTPs), based on the request URI, a secret key and the current time. This implementation is based on Time based One-Time-Passwords (TOTP). Because request URIs are used, it protects against phishing at the same time.

## Implementation details

As a base, TOTP is used.

To generate a UOTP key, use HKDF-extract with the URI as the salt, and the shared secret as data, use the same hash-algorithm as used for TOTP. Proceed now with the generation of the TOTP-token. Important: Implementations MUST only store the shared secret, not the derived one. This makes ist a) possible for companys to change adress layout of their website and b) ensure other sites can't get the one-time-password.


## Implementations

This repository contains examples in JS and python. 


