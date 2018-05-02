# Illuminati

Utilities for logging and monitoring. Includes Logstash and StatsD applications.

![Logo](priv/icon.png)

## Installation

Add `illuminati` to your list of dependencies in `mix.exs`:

```elixir
def deps do
  [
    {:illuminati, "heathmont/illuminati"}
  ]
end
```

## Configuration

Logstash and StatsD applications should be configured in your application `config/*.exs` files like this:

```elixir
config :logger,
  backends: [
    :console,
    {LogstashJson.Console, :json}
  ]

config :ex_statsd,
  host: "your.statsd.host.com",
  port: 1234,
  namespace: "your-app",
  tags: ["env:#{Mix.env}"]
```
