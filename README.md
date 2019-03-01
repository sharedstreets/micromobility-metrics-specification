# micromobility-metrics-specification

## 🚨pre-alpha: this specification is not yet stable

An open standard for calculating and communicating micromobility provider measurements.

## License

The Micromobility Metrics Specification is shared under the [MIT License](./LICENSE).

## Versions

Versions are deliniated using [semver](https://semver.org/) (semantic versioning), with the format `MAJOR.MINOR.PATCH`. Each version of the Micromobility Metrics Specification will target a specific version of the [City of Los Angeles' Mobility Data Specification (MDS) Provider API](https://github.com/CityOfLosAngeles/mobility-data-specification/tree/master/provider#versioning).

## Changelog

The [Changelog](./CHANGELOG.md) describes high level summaries of significant changes per release.

## Code of Conduct

Contributions must comply with the project's [Code of Conduct](CODE_OF_CONDUCT.md), which is based off the [v1.4 Contributor's Covenant](https://www.contributor-covenant.org/version/1/4/code-of-conduct).

## Contributing

The Micromobility Metrics Specification is a collaborative standard. To propose changes, ask questions, or flag issues, please follow the [Contributing](./CONTRIBUTING.md) documentation.

## Implementations

- [SharedStreets Micromobility Connector](https://github.com/sharedstreets/sharedstreets-micromobility-connector)

## Compliance

Each version of the Micromobility Metrics Specification will include a test suite with an implementation of an HTTP service following the [City of Los Angeles' Mobility Data Specification (MDS) Provider API](https://github.com/CityOfLosAngeles/mobility-data-specification/tree/master/provider). Implememtations of the Micromobility Metrics Specification should run this test suite to ensure standards compliance and reporting accuracy.
