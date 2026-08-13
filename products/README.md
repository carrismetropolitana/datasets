# Dataset PRODUCTS

## Overview

This dataset contains **transport product titles** and classification flags used to identify whether a product represents a person/transport title and whether it is associated with a **junior** or **senior** passenger category.

The dataset contains approximately **1,000 product records**.

## Columns

| Column                      | Description                                                                         | Type      |
| --------------------------- | ----------------------------------------------------------------------------------- | --------- |
| `Product_id`                | Unique identifier for the transport product                                         | `string`  |
| `Name`                      | Human-readable product/title name                                                   | `string`  |
| `is_person_transport_title` | Indicates whether the product is considered a person-related transport title        | `boolean` |
| `is_junior`                 | Indicates whether the title is associated with a junior/under-23 passenger category | `boolean` |
| `is_senior`                 | Indicates whether the title is associated with a senior/65+ or equivalent category  | `boolean` |

## Classification Rules

### `is_person_transport_title`

`is_person_transport_title = False` when the `Name` contains terms associated with non-person transport products or administrative/other items.

### `is_junior`

`is_junior = True` when the product name contains indicators of a junior/younger passenger category.

### `is_senior`

`is_senior = True` when the product name contains indicators of a senior/passenger concession category.


## Important Notes

* Classification is based on **keywords contained in `Name`** and not on structured product metadata.
* `is_person_transport_title` is independent from `is_junior` and `is_senior`. For example, a product can be both a person transport title and a junior title.
* A product may also have `is_person_transport_title = False` while `is_junior = True`, as seen with administrative products containing `sub23` or similar terminology.

