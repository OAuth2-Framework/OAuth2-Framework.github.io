# OAuth2 Framework Initiative

Ce projet vise à proposer tous les éléments nécessaires à la création d'un serveur d'autorisation basé sur le protocole OAuth2.

Ci-dessous une liste des composants mis à votre disposition :

* Gestion des _Access Token_ :
  * _Access Token_ basé sur des Json Web Tokens (JWT)
  * _Access Token_ basé sur une chaine aléatoire
  * Possibilité d'utiliser un autre gestionnaire
* Types de Tokens :
  * _Bearer Access Token_ ([RFC6750](https://tools.ietf.org/html/rfc6750))
  * _MAC Access Token_ ([IETF draft 02 only](https://tools.ietf.org/html/draft-ietf-oauth-v2-http-mac-02)) - _L'implémentation est arrêtée. Il sera préférable d'utiliser les POP Access Tokens dès leur mise à disposition_
  * Possibilité d'utiliser un autre type de Tokens
* [x] Gestionnaire de Scopes ([RFC6749, section 3.3](https://tools.ietf.org/html/rfc6749#section-3.3))
  * Application d'une politique si aucun scope n'est demandé
    * Ne rien faire
    * Émettre une erreur
    * Attribuer un/des scope(s) par défaut
    * Possibilité d'utiliser une politique personnalisée
* Gestionnaire de clients:
  * Clients publics ([RFC6749, section 2.1](https://tools.ietf.org/html/rfc6749#section-2.1)) - Voir `none`
  * Clients avec mot de passe ([RFC6749, section 2.3.1](https://tools.ietf.org/html/rfc6749#section-2.3.1))
    * Authentification par la méthode HTTP Basic ([RFC2617](https://tools.ietf.org/html/rfc2617) and [RFC7617](https://tools.ietf.org/html/rfc7617)) - Voir `client_secret_basic`
    * Authentification par assertion JWT (le mot de passe en tant que clé partagée) ([OpenID Connect Core](http://openid.net/specs/openid-connect-core-1_0.html#Signing)) - Voir `client_secret_jwt` 
    * Authentification par mot de passe dans le corps de la requête - Voir`client_secret_post` 
  * Clients avec assertion SAML ([RFC7521](https://tools.ietf.org/html/rfc7521) and [RFC7522](https://tools.ietf.org/html/rfc7522))
  * Clients avec assertion JWT ([RFC7521](https://tools.ietf.org/html/rfc7521) and [RFC7523](https://tools.ietf.org/html/rfc7523)) - Voir `private_key_jwt` 
  * Possibilité d'utiliser d'autres méchanismes d'authentification
* Points d'entrée :
  * Authorisation ([RFC6749, section 3.1](https://tools.ietf.org/html/rfc6749#section-3.1))
  * Token ([RFC6749, section 3.2](https://tools.ietf.org/html/rfc6749#section-3.2))
  * Révocation des Token ([RFC7009](https://tools.ietf.org/html/rfc7009))
  * Introspection des Token ([RFC7662](https://tools.ietf.org/html/rfc7662))
  * Enregistrement dynamique des client ([RFC7591](https://tools.ietf.org/html/rfc7591))
  * Configuration dynamique des clients ([RFC7592](https://tools.ietf.org/html/rfc7592))
  * Metadata
  * Clés de signature/chiffrement
  * Information utilisateur (`Userinfo`)
  * iFrame pour gestion de la session utilisateur
  * Issuer Discovery
* Flux d'Autorisation :
  * _Authorization Code_ ([RFC6749, section 4.1](https://tools.ietf.org/html/rfc6749#section-4.1))
    * _Proof Key for Code Exchange by OAuth Public Clients_ ([RFC7636](https://tools.ietf.org/html/rfc7636))
      * _Plain_
      * _S256_
      * Possibilité d'utiliser d'autres méthodes
  * _Implicit_ ([RFC6749, section 4.2](https://tools.ietf.org/html/rfc6749#section-4.2))
  * _Resource Owner Password Credentials_ ([RFC6749, section 4.3](https://tools.ietf.org/html/rfc6749#section-4.3))
  * _Client credentials_ ([RFC6749, section 4.4](https://tools.ietf.org/html/rfc6749#section-4.4))
  * _Refresh Token_ ([RFC6749, section 6](https://tools.ietf.org/html/rfc6749#section-6))
  * _SAML Bearer Token_ ([RFC7521](https://tools.ietf.org/html/rfc7521) and [RFC7522](https://tools.ietf.org/html/rfc7522))
  * _JWT Bearer Token_ ([RFC7521](https://tools.ietf.org/html/rfc7521) and [RFC7523](https://tools.ietf.org/html/rfc7523))
  * Possibilité d'utiliser d'autres flux d'autorisation

* Implementation partielle :
  * Threat Model and Security Consideration ([RFC6819](https://tools.ietf.org/html/rfc6819))

* Intégration prévue :
  * _POP Access Token_ ([Proof-of-Possession (PoP) Security Architecture](https://tools.ietf.org/html/draft-ietf-oauth-pop-architecture), [Proof-of-Possession: Authorization Server to Client Key Distribution](https://tools.ietf.org/html/draft-ietf-oauth-pop-key-distribution) et [Proof-of-Possession Key Semantics for JSON Web Tokens (JWTs)](https://tools.ietf.org/html/rfc7800))
  * [A Method for Signing an HTTP Requests for OAuth](https://tools.ietf.org/html/draft-ietf-oauth-signed-http-request)
  * [Token Exchange: An STS for the REST of Us](https://tools.ietf.org/html/draft-ietf-oauth-token-exchange)
