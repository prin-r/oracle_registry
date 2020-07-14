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

- Source1
  - DataProvider<CurrencyId, Price>
- Source2
  - DataProvider<CurrencyId, Price>
- Source3
  - DataProvider<CurrencyId, Price>
.
.
.
- SourceN
  - DataProvider<CurrencyId, Price>

# Methods

- get(data_provider_id: &str, key: &CurrencyId) -> Option<Price>
    - match data_provider_id
      - "Source1" => Source1::get(&key),
      - "Source2" => Source2::get(&key),
      - "Source3" => Source3::get(&key),
      .
      .
      .
      - "SourceN" => SourceN::get(&key),
