## Changelog

**{{site.base_gateway}} 3.4.x**
* The `redis` strategy now catches strategy connection failures.

* The `/consumer_groups/:id/overrides` endpoint has been deprecated. While this endpoint will still function, we strongly recommend transitioning to the new and improved method for managing consumer groups, as documented in the [Enforcing rate limiting tiers with the Rate Limiting Advanced plugin](/hub/kong-inc/rate-limiting-advanced/how-to/) guide. You can also find detailed information on creating consumer groups in the [API Documentation](https://developer.konghq.com/spec/937dcdd7-4485-47dc-af5f-b805d562552f/25d728a0-cfe3-4cf4-8e90-93a5bb15cfd9#/default/post-consumer_groups).

**{{site.base_gateway}} 3.2.1**
* The shared Redis connector now supports username + password authentication for cluster connections, improving on the existing single-node connection support. This automatically applies to all plugins using the shared Redis configuration.

**{{site.base_gateway}} 3.1.x**
* Added the ability to customize the error code and message with
the configuration parameters `error_code` and `error_message`.

**{{site.base_gateway}} 3.0.x**

* {{site.base_gateway}} now disallows enabling the plugin if the `cluster`
strategy is set with DB-less or hybrid mode.

**{{site.base_gateway}} 2.8.x**

* Added the `redis.username` and `redis.sentinel_username` configuration parameters.

* The `redis.username`, `redis.password`, `redis.sentinel_username`, and `redis.sentinel_password`
configuration fields are now marked as referenceable, which means they can be securely stored as
[secrets](/gateway/latest/kong-enterprise/secrets-management/getting-started)
in a vault. References must follow a [specific format](/gateway/latest/kong-enterprise/secrets-management/reference-format/).

**{{site.base_gateway}} 2.7.x**

* Added the `enforce_consumer_groups` and `consumer_groups` configuration parameters.

**{{site.base_gateway}} 2.5.x**

* Deprecated the `timeout` field and replaces it with three precise options: `connect_timeout`, `read_timeout`, and `send_timeout`.
* Added `redis.keepalive_pool`, `redis.keepalive_pool_size`, and `redis.keepalive_backlog` configuration options.
* `ssl_verify` and `server_name` configuration options now support Redis Sentinel-based connections.

**{{site.base_gateway}} 2.2.x**
* Added the `redis.ssl`, `redis.ssl_verify`, and `redis.server_name` parameters for configuring TLS connections.
