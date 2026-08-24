# Matrix OpenID Connect project playground environment

**This playground has been decommissioned and is no longer available.** The
homeservers, authentication servers and clients it hosted on `*.element.dev`
have been shut down.

It was provided by [Element](https://element.io/) to give the ecosystem
somewhere to try out next-generation authentication
([MSC3861](https://github.com/matrix-org/matrix-spec-proposals/pull/3861)) while
it was still being designed and no public deployment existed.

Next-generation authentication is now part of the Matrix specification as of
[v1.15](https://spec.matrix.org/v1.15/client-server-api/#authentication), and is
deployed on public homeservers, so a separate playground is no longer needed.

If you want to try it out or develop against it:

- point your client at a homeserver which supports it, such as `matrix.org`;
- to run your own, deploy [Synapse](https://github.com/element-hq/synapse)
  together with the
  [Matrix Authentication Service](https://github.com/element-hq/matrix-authentication-service);
- the [client implementation guide](https://areweoidcyet.com/client-implementation-guide/)
  walks through the flows interactively.
