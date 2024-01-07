# Eventide Gen 3 Collapse Storage Namespaces

## Projects

### message-store (and message-store-postgres)

#### Prep

- Remove vestigial package tests
- Review whether tools/write_message.rb is still needed
- Consider whether Get Substitute should have its own tests
  - Get::Substitute is what’s returned by Controls::Get, so Get::Substitute still gets exercised by the test suite.

#### Code Migration

- Settings
  - settings/message_store.json, rather than settings/message_store_postgres.json
- Session
- Put
- Write (combine MS::Write module with MS::PG::Write class)
- Get (combine MS::Get module with MS::PG::Get module)
- Get Condition
- Get Category (including ConsumerGroup and Correlation)
- Get Stream
- Get Stream Last (combine MS::Get::Stream::Last module with MS::PG::Get::Stream::Last class)
- Read (combine MS::Read module with MS::PG::Read class)
- Interactive tests
- Benchmarks
- Readme

### messaging (and messaging-postgres)

#### Code Migration

- Write (combine Msg::Write module with Msg::PG::Write class)
- Interactive tests

### entity-store (entity-snapshot-postgres, entity-store-postgres-test)

#### Prep

- The reader macro should be removed, since it’s primary purpose is to vary the reader implementation
  - The reader macro’s batch_size parameter must be considered
- The snapshot macro should be either removed or reworked, since it’s primary purpose is to specify a snapshot implementation
  - The snapshot macro’s interval parameter must be considered

#### Code Migration

TBD

### consumer (and consumer-postgres)

#### Code Migration

- Position Store (combine Consumer::PositionStore module and Consumer::PG::PositionStore class)
  - Recorded message
  - Stream Name
- Consumer (combine Consumer module and Consumer::PG class)
  - Identifier::Error

### eventide

- New library
- Depends on consumer and entity_store

### Archive Libraries

- eventide-postgres
- message-store-postgres
- messaging-postgres
- entity-snapshot-postgres
- entity-store-postgres-test
- consumer-postgres
- message-store-event-store
- messaging-event-store
- entity-store-event-store-test
- consumer-event-store
- entity-snapshot-event-store
- eventide-event-store
- event-store-http
- event-store-utils
