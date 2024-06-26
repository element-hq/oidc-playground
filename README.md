# Matrix OpenID Connect project playground environment

This playground environment is provided by [Element](https://element.io/) in support of the project to migrate the Matrix ecosystem to OIDC as proposed in [MSC3861](https://github.com/matrix-org/matrix-spec-proposals/pull/3861).

You can use the playground to try out the latest developments and also as a test bed for development.

As a recap, a key goal of the project is to allow Matrix Homeservers to delegate auth to a separate server (using the OIDC standard) which would replace the current auth system built into the Homeserver.

This means that rather than registering a user directly on a Homeserver instead you do the registration on an OpenID Provider (auth server).

# Homeservers + OpenID Providers to try

The homeservers in the playground run Synapse with the experimental `msc3861` feature enabled that delegates to OIDC. They aren't federated so you can't access your regular Matrix rooms.

We may also need to reset the playground in future so don't use it for anything important!

The following homeserver + OpenID Provider combinations are available to try out:

<a name="homeservers-table"></a>
| Address | Homeserver | Sliding Sync Proxy | OpenID Provider | Supports MSC4108?\* | Supports legacy clients?\*\* | Supports open client registration?\*\*\* | Notes |
| --- | --- | --- | --- | --- | --- | --- | --- |
| `synapse-oidc.element.dev` | Synapse | ✅ | [Matrix Authentication Service](https://github.com/matrix-org/matrix-authentication-service) | ✅ | ✅ | ✅ | Currently you can only register with a username/password (SSO/social login and others are to come) |
| `synapse-keycloak-oidc.element.dev` | Synapse | ✅ | [Keycloak](https://www.keycloak.org) | ✅ | ❌ | ⚠ | CORS is currently misconfigured so client registration won't work from a web browser |

\* allows sign in to be completed by scanning QR code on another device

\*\* "legacy" means a client that is not OIDC-native

\*\*\* if open client registration is supported it means that any client can register to use the OP. Open client registration is like how non-OIDC-enabled Homeservers operate today.

# Clients/Applications to try

You can use one of these to register and login on one or more of the OIDC enabled homeservers:

<a name="clients-table"></a>
| Client | Implementation type | Supports QR login via Device Flow?\* | Configured with static client ID for `synapse-keycloak`? |
| --- | --- | --- | --- |
| [Hydrogen](https://hydrogen-oidc.element.dev/) | OIDC-native | ❌ | ✅ |
| [Files SDK Demo](https://files-sdk-demo-oidc.element.dev/) | OIDC-native | ✅ | ✅ |
| [Element Web](https://element-oidc.element.dev/) | OIDC-aware | n/a | n/a |

Additionally, you can try using the client compatibility layer with any other client connecting using homeserver: `synapse-oidc.element.dev`

The compatibility layer works best with a client that supports SSO (login and register are supported) but otherwise you can login using password (having registered using another client or directly on the auth server at https://auth-oidc.element.dev).

# Limitations

Notable limitations:

- None at the moment

# Sign in with QR code

You can use the `synapse-oidc.element.dev` homeserver to try out the [MSC4108](https://github.com/matrix-org/matrix-spec-proposals/pull/4108) feature that allows you to use a QR code to sign in and cross-sign a new device.
