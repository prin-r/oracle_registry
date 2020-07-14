# Overview

The current abstraction have already enable any defi module to connect with any oracle modules that it wants to. However, it is not possible for a module switch the oracle at runtime. Therefore, hardfork is the only way to go.

We would like to present the oracle registry module specification which we believe will make oracle switching possible at runtime.

The oracle registry module have only one main functionality which is being the hub of all oracle modules in order to enable any defi module to connect with each oracle via oracle registry module. Therefore, oracle switching at runtime is possible.

This document only consider phrase one.

# Dependency

- module-primitives
  - CurrencyId
- module-support
  - Price
- orml_traits
  - DataProvider

# Type

- trait DataProviderRegistry<Key, Value>
  - get(data_provider_id: &str, key: &Key) -> Option<Value>

# Trait

- Source1: DataProvider<CurrencyId, Price>
- Source2: DataProvider<CurrencyId, Price>
- Source3: DataProvider<CurrencyId, Price>
- ...
- SourceN: DataProvider<CurrencyId, Price>

# Methods

- get(data_provider_id: &str, key: &CurrencyId) -> Option<Price>
    - match data_provider_id
      - "Source1" => Source1::get(&key),
      - "Source2" => Source2::get(&key),
      - "Source3" => Source3::get(&key),
      - ...
      - "SourceN" => SourceN::get(&key),
      - _ => None
