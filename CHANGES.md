# Eventide Changes

### 2.0.0.0

## Postgres Message Store

- Database management tool output is clarified
- All server function parameter names are no longer named with underscore prefixes (eg: `_stream_name` is renamed to `stream_name`)
- Indexes are no longer built with the `CONCURRENTLY` option
- Indexes include correlation metadata
- The messages_stream_name_position_uniq_idx is removed and replaced with the messages_stream_name_position_correlation_uniq_idx
- The messages_category_global_position_idx is removed and replaced with the messages_category_global_position_correlation_idx
- The `role` file system namespace is renamed to `access-control`
- The retrieval server functions, `get_stream_messages` and `get_category_messages`, support pub/sub directly by receiving a `correlation` argument and composing the correlation metadata query condition direction in the server function
- The retrieval server functions provide debugging output that is activated via the Postgres setting, `message_store.debug_get`
- The write server function provides debugging output that is activated via the Postgres setting, `message_store.debug_write`
- The `message_store.debug` Postgres setting activates both the retrieval and write debug output
- Improvements to interactive tests
