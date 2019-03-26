Micromobility Metrics Specification
---

# 1. Introduction

## 1.1 Requirements Language

The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED", "NOT RECOMMENDED", "MAY", and "OPTIONAL" in this document are to be interpreted as described in [RFC2119](https://www.ietf.org/rfc/rfc2119.txt).

# 2. Purpose

This specification describes a standard data interchange format for the communication of metrics related to high level micromobility usage across a region, such as a city. These metrics are used in both the allocation of micro transit infrastructure, as well as enforcement of policy carried out by regulatory authorities. This document describes a shared method for calculating these statistics from raw telematics data.

# 3. Encoding

## 3.1 Data Interchange Format

The Micromobility Metrics Specification is an object level string encoding. The structure of the data MUST comply with the [RFC8259 JSON Format](https://tools.ietf.org/html/rfc8259).

## 3.2 File Format

This specification does not specify a custom tailored file format for storage. A text file with a .json extension MAY be used as described in [RFC8259 JSON Format](https://tools.ietf.org/html/rfc8259) OR data MAY be encoded as a valid [RFC 7464 JSON Text Sequence](https://tools.ietf.org/html/rfc7464).

# 4. Structure

Each metric described MUST each of a common set of attributes, listed here.

## 4.1 Description

A summary of the metric.

## 4.2 Spatial

A list of valid spatial dimensions that may be aggregated to create the metric. Valid spatial dimensions are as follows:

### 4.2.1

"GLOBAL"

### 4.2.2

"SHST"

### 4.2.3

"H3"

## 4.3 Temporal

A list of valid temporal dimensions that may be aggregated to create the metric. Valid spatial dimensions are as follows:

### 4.3.1

"LIVE"

### 4.3.2

"1H"

# 5. Metrics

## 5.1 Vehicles

### 5.1.1 Description

Count of unique vehicles.

### 5.1.2 Spatial

MUST be exactly one of the following: "GLOBAL", "H3", "SHST".

### 5.1.3 Temporal

MUST be exactly one of the following: "1H".

### 5.1.4 Minimum Filter

The minimum filter MUST be greater or equal to 2.

### 5.1.5 Source

This metric is aggregated from the `/trips` MDS Provider source.

### 5.1.6

```json
{
  "metric": "vehicles",
  "spatial": "H3",
  "temporal": "1H",
  "space": "123",
  "time": "2019-02-17-160",
  "value": 1000
}
```



## 5.2 Utilization

### 5.2.1 Description

Aggregate percentage of time any vehicles in zone were in use.

### 5.2.2 Spatial

MUST be exactly one of the following: "GLOBAL", "H3".

### 5.2.3 Temporal

MUST be exactly one of the following: "LIVE", "1H".

### 5.2.4 Minimum Filter

N/A

### 5.2.5 Source

This metric is aggregated from the `/status_changes` MDS Provider source.

### 5.2.6

```json
{
  "metric": "utilization",
  "spatial": "H3",
  "temporal": "1H",
  "space": "123",
  "time": "2019-02-17-160",
  "value": 0.5
}
```



## 5.3 Availability

### 5.3.1 Description

Aggregate percentage of time any vehicles in zone were not in use.

### 5.3.2 Spatial

MUST be exactly one of the following: "GLOBAL", "H3".

### 5.3.3 Temporal

MUST be exactly one of the following: "LIVE", "1H".

### 5.3.4 Minimum Filter

N/A

### 5.3.5 Source

This metric is aggregated from the `/status_changes` MDS Provider source.

### 5.3.6

```json
{
  "metric": "availability",
  "spatial": "H3",
  "temporal": "1H",
  "space": "123",
  "time": "2019-02-17-160",
  "value": 0.5
}
```



## 5.4 Pickups

### 5.4.1 Description

Count of unique trips starting in the zone.

### 5.4.2 Spatial

MUST be exactly one of the following: "GLOBAL", "H3", "SHST".

### 5.4.3 Temporal

MUST be exactly one of the following: "1H".

### 5.4.4 Minimum Filter

The minimum filter MUST be greater or equal to 2.

### 5.4.5 Source

This metric is aggregated from the `/trips` MDS Provider source.

### 5.4.6

```json
{
  "metric": "pickups",
  "spatial": "H3",
  "temporal": "1H",
  "space": "123",
  "time": "2019-02-17-160",
  "value": 100
}
```


## 5.5 Dropoffs

### 5.5.1 Description

Count of unique trips ending in the zone.

### 5.5.2 Spatial

MUST be exactly one of the following: "GLOBAL", "H3", "SHST".

### 5.5.3 Temporal

MUST be exactly one of the following: "1H".

### 5.5.4 Minimum Filter

The minimum filter MUST be greater or equal to 2.

### 5.5.5 Source

This metric is aggregated from the `/trips` MDS Provider source.

### 5.5.6

```json
{
  "metric": "dropoffs",
  "spatial": "H3",
  "temporal": "1H",
  "space": "123",
  "time": "2019-02-17-160",
  "value": 100
}
```



## 5.6 Pickups Matrix

### 5.6.1 Description

Count of unique trips starting in each zone that ended within the zone.

### 5.6.2 Spatial

MUST be exactly one of the following: "H3".

### 5.6.3 Temporal

MUST be exactly one of the following: "1H".

### 5.6.4 Minimum Filter

The minimum filter MUST be greater or equal to 5.

### 5.6.5 Source

This metric is aggregated from the `/trips` MDS Provider source.

### 5.6.6

```json
{
  "metric": "pickupsmatrix",
  "spatial": "H3",
  "temporal": "1H",
  "space1": "123",
  "space2": "321",
  "time": "2019-02-17-160",
  "value": 20
}
```



## 5.7 Dropoffs Matrix

### 5.7.1 Description

Count of unique trips ending in each zone that ended within the zone.

### 5.7.2 Spatial

MUST be exactly one of the following: "H3".

### 5.7.3 Temporal

MUST be exactly one of the following: "1H".

### 5.7.4 Minimum Filter

The minimum filter MUST be greater or equal to 5.

### 5.7.5 Source

This metric is aggregated from the `/trips` MDS Provider source.

### 5.7.6

```json
{
  "metric": "dropoffsmatrix",
  "spatial": "H3",
  "temporal": "1H",
  "space1": "123",
  "space2": "321",
  "time": "2019-02-17-160",
  "value": 20
}
```
