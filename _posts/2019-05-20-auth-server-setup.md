---
layout: post
title:  "Setup an Authentication Server using ASP.NET Core 2.2 and Identity Server 4"
date:   2019-05-20T13:20:00Z
categories: security
---

#### Goal
Set up a standalone authentication server (federation gateway?) using ASP.NET Core 2.2 and Identity Server 4,
with plans to migrate to Core 3.0 when released in the fall of 2019.

* Install Core 2.2 SDK

* For Google sign-on:
  * Register IdentityServer4 as Oauth *web server* type. Set redirect uri as IdentityServer4 base url plus "/signin-google". Get Client Id and Client Secret
  * [https://developers.google.com/identity/sign-in/web/sign-in](https://developers.google.com/identity/sign-in/web/sign-in)
  
* For Okta sign-on:
  * Register for account, get Okta domain (dev-*.okta.com)
  * Create new application: Web type (for access from IdentityServer4 mvc app login page)
  * Set grant types (auth code, implicit, ...)
  * set login redirect uri (https://(uri to ids4 app)/signin-oidc)
  * set logout redirect uri (https://(uri to ids4 app)/signout-callback-oidc)
  * set initiate login uri (https://(uri to ids4 app)/authorization-code/callback)
  * Get client id and secret for use in IdentityServer4 setup. In Startup.ConfigureServices, add AddOpenIdConnect().
  
* Add PKCE (Proof Key for Code Exchange)
  * [https://damienbod.com/2018/04/25/oauth-authentication-with-pkce-for-a-net-core-console-native-application/](https://damienbod.com/2018/04/25/oauth-authentication-with-pkce-for-a-net-core-console-native-application/)
  * [https://www.scottbrady91.com/OpenID-Connect/ASPNET-Core-using-Proof-Key-for-Code-Exchange-PKCE](https://www.scottbrady91.com/OpenID-Connect/ASPNET-Core-using-Proof-Key-for-Code-Exchange-PKCE)
  
#### References:

* [https://identityserver4.readthedocs.io/en/latest/topics/federation_gateway.html](https://identityserver4.readthedocs.io/en/latest/topics/federation_gateway.html)
* [https://github.com/BenjaminAbt/Samples.AspNetCore-IdentityServer4](https://github.com/BenjaminAbt/Samples.AspNetCore-IdentityServer4)
* []()
* []()
* []()