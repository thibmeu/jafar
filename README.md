# JAFAR IP Prefix Publication Schema

![License](https://img.shields.io/github/license/thibmeu/jafar)

This repository contains the [JSON Schema](https://json-schema.org/) implementation for JAFAR (JSON-Based Format for Publishing IP Ranges of Automated HTTP Clients), as defined in [draft-illyes-aipref-jafar-00](https://datatracker.ietf.org/doc/html/draft-illyes-aipref-jafar-00).

JAFAR provides a machine-readable format for automated HTTP client operators (web crawlers, AI bots, etc.) to publish their IP address ranges, enabling website operators to identify and verify legitimate automated traffic.

## Table of Contents

- [Features](#features)
- [Real-World Examples](#real-world-examples)
- [Usage](#usage)
- [Security Considerations](#security-considerations)
- [License](#license)

## Features

- JAFAR validation, including IPv4 and IPv6 prefixes
- JSON Schema 2020-12 compliant
- Schema URL `https://raw.githubusercontent.com/thibmeu/jafar/refs/heads/draft-illyes-aipref-jafar-00/schema.json`

## Real-World Examples

The following services publish IP ranges in JAFAR-adjacent formats:

| Service                 | URL                                                                             |
| ----------------------- | ------------------------------------------------------------------------------- |
| Googlebot               | https://developers.google.com/static/search/apis/ipranges/googlebot.json        |
| Google Special Crawlers | https://developers.google.com/static/search/apis/ipranges/special-crawlers.json |
| Bingbot                 | https://www.bing.com/toolbox/bingbot.json                                       |

## Usage

The JSON Schema is provided in [schema.json](./schema.json).

### Editor Integration

Add `$schema` to your JAFAR documents for IDE autocompletion and inline validation:

```json
{
  "$schema": "https://raw.githubusercontent.com/thibmeu/jafar/refs/heads/draft-illyes-aipref-jafar-00/schema.json",
  "formatVersion": "1.0",
  "synctoken": "...",
  "creationTime": "2025-08-15T14:30:00Z",
  "prefixes": [...]
}
```

### Validation

You can validate JAFAR documents using any JSON Schema 2020-12 compliant validator.

| Language   | Tool                                                                        | Command                                                                 |
| ---------- | --------------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| JavaScript | [ajv-cli](https://github.com/ajv-validator/ajv-cli)                         | `ajv validate --spec=draft2020 -c ajv-formats -s schema.json -d <file>` |
| Rust       | [jsonschema-rs](https://github.com/Stranger6667/jsonschema)                 | `jsonschema-cli schema.json -i <file>`                                  |
| Python     | [jsonschema](https://github.com/python-jsonschema/jsonschema)               | `jsonschema -i <file> schema.json`                                      |
| Go         | [santhosh-tekuri/jsonschema](https://github.com/santhosh-tekuri/jsonschema) | `jv schema.json <file>`                                                 |

For a comprehensive list, see [JSON Schema Implementations](https://json-schema.org/implementations).

## Security Considerations

This software has not been audited. Please use at your sole discretion.

## License

This project is under the MIT license.

### Contribution

Unless you explicitly state otherwise, any contribution intentionally submitted for inclusion in the work by you shall be MIT licensed as above, without any additional terms or conditions.
