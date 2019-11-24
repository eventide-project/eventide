# Eventide Changes

### 2.0.0.0

## Postgres Message Store

- The `get_category_messages` server function supports pub/sub directly by receiving a `correlation` argument and composing the correlation metadata query condition directly in the server function [http://docs.eventide-project.org/user-guide/message-store/server-functions.html#get-messages-from-a-stream](http://docs.eventide-project.org/user-guide/message-store/server-functions.html#get-messages-from-a-stream)
- The `get_category_messages` server function supports consumer groups via the `consumer_group_member` and `consumer_group_size` parameters [http://docs.eventide-project.org/user-guide/message-store/server-functions.html#get-messages-from-a-category](http://docs.eventide-project.org/user-guide/message-store/server-functions.html#get-messages-from-a-category)
- The retrieval server functions provide debugging output that is activated via the Postgres setting, `message_store.debug_get` [http://docs.eventide-project.org/user-guide/message-store/server-functions.html#debugging-output](http://docs.eventide-project.org/user-guide/message-store/server-functions.html#debugging-output)
- The write server function provides debugging output that is activated via the Postgres setting, `message_store.debug_write` [http://docs.eventide-project.org/user-guide/message-store/server-functions.html#debugging-output](http://docs.eventide-project.org/user-guide/message-store/server-functions.html#debugging-output)
- The `message_store.debug` Postgres setting activates both the retrieval and write debug output [http://docs.eventide-project.org/user-guide/message-store/server-functions.html#debugging-output](http://docs.eventide-project.org/user-guide/message-store/server-functions.html#debugging-output)
- `id` stream parsing function [http://docs.eventide-project.org/user-guide/message-store/server-functions.html#get-the-id-from-a-stream-name](http://docs.eventide-project.org/user-guide/message-store/server-functions.html#get-the-id-from-a-stream-name)
- `cardinal_id` stream parsing function [http://docs.eventide-project.org/user-guide/message-store/server-functions.html#get-the-cardinal-id-from-a-stream-name](http://docs.eventide-project.org/user-guide/message-store/server-functions.html#get-the-cardinal-id-from-a-stream-name)
- Database management tool output is clarified
- All server function parameter names are no longer named with underscore prefixes (http://docs.eventide-project.org/user-guide/message-store/server-functions.html)
- Indexes are no longer built with the `CONCURRENTLY` option (http://docs.eventide-project.org/user-guide/message-store/anatomy.html#source-code)
- The messages_category_global_position_idx is removed and replaced with the messages_category_global_position_correlation_idx, which includes correlation metadata
- Improvements to interactive tests (https://github.com/eventide-project/postgres-message-store/tree/master/test)

## Message Store Client

- MessageStore::Postgres::Get receives the `correlation` argument and passes it to the message store database's retrieval functions (http://docs.eventide-project.org/user-guide/retrieving/batch.html#retrieving-correlated-messages)
- MessageStore::Postgres::Get receives the `consumer_group_member` and `consumer_group_size` arguments and passes it to the message store database's retrieval functions (http://docs.eventide-project.org/user-guide/retrieving/batch.html#consumer-groups)
- Stream name utilities now support stream name with compound IDs (http://docs.eventide-project.org/user-guide/stream-names/message-store-stream-name.html#stream-name)
- Cardinal IDs are formalized as part of the stream name utilities (http://docs.eventide-project.org/user-guide/stream-names/message-store-stream-name.html#stream-name)
- Correlation error raised by the message store database is caught, coerced to `MessageStore::Correlation::Error` and re-raised by the `Get` class

## Consumer

- Entity stream names are no longer supported by consumers (Only categories can be consumed)
- Correlation query conditions are no longer composed in the consumer and passed to the message store database server functions
- Consumer group query conditions are no longer composed in the consumer and passed to the message store database server functions

## Documentation

- The `MessageStore::Postgres::Get` class is documented (http://docs.eventide-project.org/user-guide/retrieving/batch.html)
- Debugging output for the Postgres server functions is documented (http://docs.eventide-project.org/user-guide/message-store/server-functions.html#debugging-output)
- The settings file location override is documented (http://docs.eventide-project.org/user-guide/session.html#overriding-the-setting-file-location)
