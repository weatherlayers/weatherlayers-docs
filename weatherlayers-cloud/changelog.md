# Changelog

### 2024.8.2

_August 23rd, 2024_

Bug fixes:

* Validate `datetimeRange` in `loadDatasetSlice`

### 2024.8.1

_August 20th, 2024_

Minor changes:

* Replace TS enums with string constants for cross-bundle compatibility between `weatherlayers-gl` and `weatherlayers-gl/client`
  * [https://www.totaltypescript.com/books/total-typescript-essentials/deriving-types#using-as-const-for-javascript-style-enums](https://www.totaltypescript.com/books/total-typescript-essentials/deriving-types#using-as-const-for-javascript-style-enums)

### 2024.8.0

_August 11th, 2024_

New features:

* Add `UnitSystem.METRIC_KILOMETERS` to allow selecting `km/h` unit

Minor changes:

* Split `UnitDefinition` interface (with `UnitSystem`) from `UnitFormat` interface (without `UnitSystem`)
* Update `datetimeRange` in `loadDataset` response to be open-ended

Bug fixes:

* Fix `referenceDatetime`, `horizon` in `loadDatasetData` response to match the returned data image

### 2024.7.0

_July 20, 2024_

New features:

* Add `datetimeStep` config property
* Add `datetime`, `referenceDatetime`, `horizon` to `loadDatasetData` response

### 2023.8.0

_September 5, 2023_

New features:

* Add `unitSystem` config property

### 2023.5.1

_May 21, 2023_

Bug fixes:

* Fix loading historical data

### 2023.4.0

_April 30, 2023_

New features:

* Add `loadDatasetSlice` function to support loading historical data

Minor changes:

* Use JSON palette instead of plain text
