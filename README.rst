coderpad-openapi
================

Shared, community-maintained OpenAPI specification for CoderPad Interview.
This is not an official CoderPad publication.

``openapi.json`` is the canonical specification for tooling such as
``coderpad-py`` and ``coderpad-cli``.
API contract changes belong here rather than in independently maintained
consumer fixtures.

Consumers
---------

Pin an immutable release tag or full commit SHA when consuming the
specification.
Resolve that dependency during installation or build preparation, not while
running tests.
Keep client-specific behavior and test assertions in the consuming
repositories.

The SDK and CLI still contain their existing copies.
Migrating those consumers to this repository is a separate follow-up.
Creating this repository does not change any installed package.

Validation
----------

.. code-block:: shell

   uvx --python 3.12 --from openapi-spec-validator==0.9.0 openapi-spec-validator openapi.json

The validation workflow runs this check on pushes and pull requests.
It also checks documentation with Vale:

.. code-block:: shell

   uvx --with docutils --from vale==3.22.0.0 vale sync
   uvx --with docutils --from vale==3.22.0.0 vale .

Provenance
----------

The initial specification and MIT license were extracted unchanged from
`adamtheturtle/coderpad <https://github.com/adamtheturtle/coderpad>`_ at commit
``114c1a57626f39e5950a58d6598e58952b487517``.
The specification was last changed there in commit
``7bfa1ac9d09651bdf22d178e9fd002acee6f6eb4``.

The relevant Git history for ``openapi.json`` and ``LICENSE`` is retained.
Extracted commit IDs differ because unrelated SDK files were removed from that
history.

Initial specification SHA-256:
``7e0533867d8ad85b0725e2c45b84f0085ec907e4930eea94a8c34f51440baf2b``.

See ``LICENSE`` for the original license and attribution.
