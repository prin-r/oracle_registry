# Overview

An oracle registry module have only one main functionality: A hub of all oracles in order to enable users to connect with each oracle via oracle registry module

This document only consider phrase one.

# Dependency

- primitives
  - CurrencyId
- support
  - Price
- orml_traits
  - DataProvider

# Type

- trait DataProviderRegistry<Key, Value>
  - get(data_provider_id: &str, key: &Key) -> Option<Value>

# Trait

- 






# Methods
