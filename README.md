# CyberChef for LazyCat

- Upstream: https://github.com/gchq/CyberChef
- Package: `community.lazycat.app.cyberchef`
- Mode: mirror; target: Linux amd64; minimum OS: 1.5.0.
- Upstream image: `ghcr.io/gchq/cyberchef`; runtime mirror: `ghcr.1ms.run/gchq/cyberchef`.
- Version follows upstream stable three-part tags; mirror verification requires matching digests.
- No database, runtime secrets, file-chooser injection or public-path bypass.
- Official store publication is disabled.

The manual workflow first smoke-tests the pinned upstream image over HTTP on port 8080, then builds the versioned LPK Release asset. Private-store publication starts disabled until the initial checks pass.

An HTTP smoke test on a GitHub runner is not a LazyCat-device installation test, nor a full browser interaction test. Import/export and recipe operations have not been end-to-end verified on a LazyCat device.

The workflow explicitly references existing organization `APPSTORE_URL`, `APPSTORE_TOKEN`, and optional `PRIVATE_STORE_GROUP_CODES` secrets. No secret values belong in this repository.
