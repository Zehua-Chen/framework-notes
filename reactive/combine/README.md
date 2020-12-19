# Concepts

## Subscribers

Subscribers consumes inputs from its upstream using `recieve(self, ...)` methods

- Some subscribers pass inputs to a downstream

- Subscribers implement `Subscriber` protocol
  - If a subscriber is not a reference type, it must explicitly implement
    `CustomCombineIdentifierConvertible`
- Subscribers are passed to publishers

## Publishers

Publishers emits outputs to its subscribers

- Subscribers are registered using `receive(self, subscriber:)`
