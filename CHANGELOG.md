# Changelog

## X.X.X

### Breaking changes

* Allow preparing the consistency level, timestamp and ttl (this is only supported from Cassandra version X.X.X)

### Non breaking changes

* Add support for potential raw prepared values via `cql-raw`

## 1.0.3

* ns change: `qbits.hayt.dsl.verb` becomes `qbits.hayt.dsl.statement`.
  This should be backward compatible as long as you don't use them
  directly, the aliases have been updated.

## 1.0.2

* Fix Collection types definitions (they were quoted)

* Fix DELETE * statement :emit (no * on delete, it now accepts nil column or :*)

## 1.0.1

* Internals change to accomodate cassaforte

## 1.0.0

* Exposed `cql-raw` and `cql-fn`, the former allows to pass arbitrary raw
  content as value, and the later allows to create function wrappers.
  These two could be usefull when/if we don't support a feature and/or
  you need lower level access to value/fn encoding.

* Added alias support

* Added ALTER DROP clause support

* tests, docstrings improvements

## 0.5.1

* Joda time support

* Moved cassandra-all in dev/test profiles

## 0.5.0

* CQL 3.0.3 support (create secondary index aka "CREATE CUSTOM INDEX")

* Added CAS support: `if-not-exists` `only-if` clauses
  https://issues.apache.org/jira/browse/CASSANDRA-5443

* Performance/ressource use improvements

* Added support for null values

* Added support for Date, blob (ByteBuffer instances), InetAddress literals

* Added noarg versions of bool clauses

* Completed/fixed coverage of blobAsX and XAsBlob functions

## 0.4.0-beta4

* Lift restriction on nil values (supported in C* 1.2.4+)

## 0.4.0-beta3

* Deprecate `q->`, since clauses/queries are just maps, use the usual
  `merge`/`assoc`/`into`. It will be removed in a future version likely 1.0.0

* Allow to use lowercased/dashed kw for permission, ex: `:full-access`
  or `:FULL_ACCESS`

* Fix `:primary-key` to allow composites

## 0.4.0-beta2

* Fix all permission queries, grant, revoke, list-permission (missing
  PERMISSION or PERMISSIONS)

* Renamed list-permission to list-perm

## 0.4.0-beta1

* cleaner AST and document (briefly) it's use in the readme
* renamed/updated the auth functions/clauses to match their cql
  counterpart more closely.

## 0.3.0

* Renamed `add` clause to `add-column` (breaking change)

* Fixed bug in batch clause (begin missing), and add missing arguments
  (UNLOGGED, COUNTER)

* Added `rename-column` `grant-user`, `revoke-user`, `alter-user`, `create-user`,
`drop-user`, `list-users`, `list-permissions`

* Added the following clauses `table`, `keyspace`, `column-family`,
  `logged`, `counter`, `resource`, `user`, `superuser`, `password`,
  `permission`, `recursive`.
