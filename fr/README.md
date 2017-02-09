# OAuth2 Framework Initiative

## Bibliothèque et bundle Symfony

Tous les éléments nécessaires à la création d'un serveur d'autorisation basé sur le protocole OAuth2 enfin disponibles.

Hautement configurable, le bundle Symfony s'ajuste à tous les besoins :

* Gestion des _Access Token_ :
  * [x] _Access Token_ basé sur JWT
  * [x] \_Access Token \_basé sur une chaine aléatoire
  * [x] Possibilité d'utiliser un qutre type de gestionnaire
* Types de Tokens :
  * [x] Bearer access token \([RFC6750](https://tools.ietf.org/html/rfc6750)\)
  * [x] MAC access token \([IETF draft 02 only](https://tools.ietf.org/html/draft-ietf-oauth-v2-http-mac-02)\) - _The implementation is stopped until the specification has not reach maturity_
  * [x] Possibilité d'utiliser un qutre type de Tokens
* [x] Gestionnaire de Scopes \([RFC6749, section 3.3](https://tools.ietf.org/html/rfc6749#section-3.3)\)
* Gestionnaire de clients:
  * [x] Clients publics \([RFC6749, section 2.1](https://tools.ietf.org/html/rfc6749#section-2.1)\) - Voir `none`
  * [x] Clients avec mot de passe \([RFC6749, section 2.3.1](https://tools.ietf.org/html/rfc6749#section-2.3.1)\)
    * [x] Authentification par la méthode HTTP Basic \([RFC2617](https://tools.ietf.org/html/rfc2617) and [RFC7617](https://tools.ietf.org/html/rfc7617)\) - Voir`client_secret_basic`
    * [x] Authentification par assertion JWT \(le mot de passe en tant que clé partagée\) \([OpenID Connect Core](http://openid.net/specs/openid-connect-core-1_0.html#Signing)\) - Voir`client_secret_jwt` 
    * [x] Authentification par mot de passe dans le corps de la requête - Voir`client_secret_post` 
  * [ ] Clients avec assertion SAML \([RFC7521](https://tools.ietf.org/html/rfc7521) and [RFC7522](https://tools.ietf.org/html/rfc7522)\)
  * [x] Clients avec assertion JWT \([RFC7521](https://tools.ietf.org/html/rfc7521) and [RFC7523](https://tools.ietf.org/html/rfc7523)\) - Voir`private_key_jwt` 
  * [x] Possibilité d'utiliser d'autres méchanismes d'authentification
* Points d'entrée :

  * [x] Authorisation \([RFC6749, section 3.1](https://tools.ietf.org/html/rfc6749#section-3.1)\)
  * [x] Token \([RFC6749, section 3.2](https://tools.ietf.org/html/rfc6749#section-3.2)\)
  * [x] Révocation des Token \([RFC7009](https://tools.ietf.org/html/rfc7009)\)
  * [x] Introspection des Token \([RFC7662](https://tools.ietf.org/html/rfc7662)\)
  * [x] Enregistrement dynamique des client \([RFC7591](https://tools.ietf.org/html/rfc7591)\)
  * [x] Configuration dynamique des clients \([RFC7592](https://tools.ietf.org/html/rfc7592)\)
  * [x] Metadata
  * [x] Clés de signature/chiffrement

* Grant types :

  * [x] Authorization code grant type \([RFC6749, section 4.1](https://tools.ietf.org/html/rfc6749#section-4.1)\)
    * [x] Proof Key for Code Exchange by OAuth Public Clients \([RFC7636](https://tools.ietf.org/html/rfc7636)\)
    * [x] Plain
    * [x] S256
    * [x] Ability to use other challenge methods
  * [x] Implicit grant type \([RFC6749, section 4.2](https://tools.ietf.org/html/rfc6749#section-4.2)\)
  * [x] Resource Owner Password Credentials grant type \([RFC6749, section 4.3](https://tools.ietf.org/html/rfc6749#section-4.3)\)
  * [x] Client credentials grant type \([RFC6749, section 4.4](https://tools.ietf.org/html/rfc6749#section-4.4)\)
  * [x] Refresh token grant type \([RFC6749, section 6](https://tools.ietf.org/html/rfc6749#section-6)\)
  * [ ] SAML grant type \([RFC7521](https://tools.ietf.org/html/rfc7521) and [RFC7522](https://tools.ietf.org/html/rfc7522)\) - _Help requested!_
  * [x] JWT Bearer token grant type \([RFC7521](https://tools.ietf.org/html/rfc7521) and [RFC7523](https://tools.ietf.org/html/rfc7523)\)
  * [x] Possibilité d'utiliser d'autres Grant Types

* Implementation partielle :

  * [ ] Threat Model and Security Consideration \([RFC6819](https://tools.ietf.org/html/rfc6819)\)
  * [ ] OpenID Connect: See [the dedicated page of its implementation](doc/OpenID_Connect_Implementation_Status.md)

* Intégration prévue :

  * [Proof-of-Possession \(PoP\) Security Architecture](https://tools.ietf.org/html/draft-ietf-oauth-pop-architecture)
  * [Proof-of-Possession: Authorization Server to Client Key Distribution](https://tools.ietf.org/html/draft-ietf-oauth-pop-key-distribution)
  * [Proof-of-Possession Key Semantics for JSON Web Tokens \(JWTs\)](https://tools.ietf.org/html/rfc7800)
  * [A Method for Signing an HTTP Requests for OAuth](https://tools.ietf.org/html/draft-ietf-oauth-signed-http-request)
  * [Token Exchange: An STS for the REST of Us](https://tools.ietf.org/html/draft-ietf-oauth-token-exchange)



