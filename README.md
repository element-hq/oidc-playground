OpenID Connect project playground environment
=
We have created a playground environment for you to try out the latest developments in the OIDC project.

As a recap, a key goal of the project is to allow Matrix Homeservers to delegate auth to a separate server (using the OIDC standard) which would replace the current auth system built into the Homeserver.

This means that rather than registering a user directly on a Homeserver instead you do the registration on an OIDC Provider (auth server).

Clients/Applications to try
==

You can use one of these to register and login using OIDC natively:

- [Hydrogen](https://hydrogen-oidc.lab.element.dev/)
- [Files SDK Demo](https://files-sdk-demo-oidc.lab.element.dev/)

Additionally, you can try using the client compatibility layer with:
- [Element Web](https://element-oidc.lab.element.dev/) - this build has some minimal changes to at least be aware of OIDC
- Or any other client connecting using homeserver: `synapse-oidc.lab.element.dev`

The compatibility layer works best with a client that supports SSO (login and register are supported) but otherwise you can login using password (having registered using another client or directly on the auth server at https://auth-oidc.lab.element.dev).

Homeservers + OIDC Providers to try
==

The homeservers in the playground tun a patched version of synapse that delegates to OIDC. They aren't federated so you can't access your regular Matrix rooms.

We may also need to reset the playground in future so don't use it for anything important!

The following homeserver + OIDC Provider combinations are available to try out:

| Address | Homeserver | OIDC Provider | Supports legacy clients? | Notes |
| - | - | - | - | - |
| `synapse-oidc.lab.element.dev` | Synapse | [Matrix Authentication Service](https://github.com/matrix-org/matrix-authentication-service) | ✅ | Currently you can only register with a username/password (SSO/social login and others are to come) |
| `synapse-okta-oidc.lab.element.dev` | Synapse | [okta.com](https://okta.com) | ❌ | Dynamic Client Registration doesn't work |
| `synapse-auth0-oidc.lab.element.dev` | Synapse | [auth0.com](https://auth0.com) | ❌ | |
