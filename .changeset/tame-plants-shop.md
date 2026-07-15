---
'@backstage/plugin-search-backend-module-elasticsearch': major
---

Upgraded the underlying Elasticsearch client to support Elasticsearch 8.x and 9.x (including the latest 9.4.x releases), in addition to 7.x. Adopters connecting to Elasticsearch (not OpenSearch) clusters running version 8 or 9 no longer need to run in legacy compatibility mode.

This is a breaking change for adopters who use `newClient()` or otherwise interact directly with the underlying Elasticsearch client obtained from this module: the client's request and response shapes changed between major versions, most notably that responses returned by the client are no longer wrapped in a `{ body, statusCode, headers }` envelope by default. Consult the Elasticsearch JavaScript client's own release notes if you depend on this behavior directly. Usage of the built-in search engine (configured via `search.elasticsearch` in `app-config.yaml`) is unaffected.
