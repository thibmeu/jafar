# JAFAR IP Prefix Publication Schema

![License](https://img.shields.io/github/license/thibmeu/jafar)

This repository contains the [JSON Schema](https://json-schema.org/) implementation for JAFAR (JSON-Based Format for Publishing IP Ranges of Automated HTTP Clients), as defined in [draft-illyes-aipref-jafar-00](https://datatracker.ietf.org/doc/html/draft-illyes-aipref-jafar-00).

JAFAR provides a machine-readable format for automated HTTP client operators (web crawlers, AI bots, etc.) to publish their IP address ranges, enabling website operators to identify and verify legitimate automated traffic.

## Tables of Content

- [Features](#features)
- [Usage](#usage)
- [Security Considerations](#security-considerations)
- [License](#license)

## Features

- JAFAR validation, including ipv4 and ipv6 prefixes
- Schema [URL](https://raw.githubusercontent.com/thibmeu/jafar/refs/heads/main/schema.json)

## Usage

The JSON Schema is provided in [schema.json](./schema.json).

You can use your favorite validation tool on the examples provided in [examples](./examples/) folder. A non exhaustive list:

- [ajv-cli](https://github.com/ajv-validator/ajv-cli) in JavaScript with `ajv validate --spec=draft2020 -s schema.json -d examples/1-basic-publication.json`
- [jsonschema](https://github.com/Stranger6667/jsonschema) in Rust with `jsonschema-cli schema.json -i examples/1-basic-publication.json`

## Security Considerations

This software has not been audited. Please use at your sole discretion.

## License

This project is under the MIT license.

### Contribution

Unless you explicitly state otherwise, any contribution intentionally submitted for inclusion in the work by you shall be MIT licensed as above, without any additional terms or conditions.
