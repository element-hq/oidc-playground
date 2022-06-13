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

Auth Server/OIDC Provider
==

Currently you can only register with a username/password (SSO/social login and others are to come).

- [Account management](https://auth-oidc.lab.element.dev/account)

Homeserver
==

The playground is running a patched synapse instance that delegates to OIDC. It isn't federated so you can't access your regular Matrix rooms.

We may also need to reset the playground in future so don't use it for anything important!
