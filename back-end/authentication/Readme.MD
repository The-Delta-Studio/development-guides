# API Authentication Feature Implementation

*This document details the variouse authentication flows used at the delta for WebApps, MobileApps, and combinations of the two.*

## Table of Contents

1. [Introduction]()
2. [Web Based Applications]()
3. [Mobile Based Applications]()
4. [Web and Mobile Aplications]()

## 1. Introduction

This document assumes a base understanding of the following concepts:

- Authentication, Authorization and the difference between. [Link](https://auth0.com/docs/authorization/authentication-and-authorization)
-  TODO

## 2. Web (or Finance Mobile) Based Applications

A combination of JWT and Refresh tokens are created for a user (User Tokens).

#### Jwt and Refresh token standards to implement
1. **JWT token life** - JWT token lifetime of 30 minutes or 1 hour. (store lifetime in appsettings)
2. **Refresh token life** - Refresh token lifetime of a of 1-24 hour/s. (store lifetime in appsettings)

## 3. Mobile Based Applications

There are two implementations that can be used for mobile applications:
- **Long-lived User Tokens** - Simpler to implement and acceptable if there is no 'critical functionality' within the application.
- **Device Tokens and User Tokens** - Required if the there is 'critical functionality' within the application.

### 3.1 Long-lived User Tokens

This method requires no device tokens to be created. Essentially the flow is exactly the same as that used fro Web applications however the standards used are different.

#### Jwt and Refresh token standards to implement
1. **JWT token life** - JWT token lifetime of 30 minutes or 1 day. (store lifetime in appsettings)
2. **Refresh token life** - Refresh token lifetime of a of 1-30 d/s. (store lifetime in appsettings)

### 3.2 Device Tokens and User Tokens

This method implement the Web application short lived user tokens and a combination of device and refresh token (Device Tokens). The device tokens are longer lived and allow for access to all 'non-critical functionality'. The User Tokens are short lived and are required for all 'critical functionality'.
