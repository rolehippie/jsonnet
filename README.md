# jsonnet

[![Source Code](https://img.shields.io/badge/github-source%20code-blue?logo=github&amp;logoColor=white)](https://github.com/rolehippie/jsonnet)
[![General Workflow](https://github.com/rolehippie/jsonnet/actions/workflows/general.yml/badge.svg)](https://github.com/rolehippie/jsonnet/actions/workflows/general.yml)
[![Readme Workflow](https://github.com/rolehippie/jsonnet/actions/workflows/readme.yml/badge.svg)](https://github.com/rolehippie/jsonnet/actions/workflows/readme.yml)
[![Galaxy Workflow](https://github.com/rolehippie/jsonnet/actions/workflows/galaxy.yml/badge.svg)](https://github.com/rolehippie/jsonnet/actions/workflows/galaxy.yml)
[![License: Apache-2.0](https://img.shields.io/github/license/rolehippie/jsonnet)](https://github.com/rolehippie/jsonnet/blob/master/LICENSE)
[![Ansible Role](https://img.shields.io/badge/role-rolehippie.jsonnet-blue)](https://galaxy.ansible.com/rolehippie/jsonnet)

Ansible role to install jsonnet configuration language.

## Sponsor

Building and improving this Ansible role have been sponsored by my current and previous employers like **[Cloudpunks GmbH](https://cloudpunks.de)** and **[Proact Deutschland GmbH](https://www.proact.eu)**.

## Table of content

- [Requirements](#requirements)
- [Default Variables](#default-variables)
  - [jsonnet_bundler_arch](#jsonnet_bundler_arch)
  - [jsonnet_bundler_download](#jsonnet_bundler_download)
  - [jsonnet_bundler_version](#jsonnet_bundler_version)
  - [jsonnet_core_arch](#jsonnet_core_arch)
  - [jsonnet_core_download](#jsonnet_core_download)
  - [jsonnet_core_includes](#jsonnet_core_includes)
  - [jsonnet_core_version](#jsonnet_core_version)
  - [jsonnet_install_path](#jsonnet_install_path)
- [Discovered Tags](#discovered-tags)
- [Dependencies](#dependencies)
- [License](#license)
- [Author](#author)

---

## Requirements

- Minimum Ansible version: `2.10`


## Default Variables

### jsonnet_bundler_arch

Architecture for jsonnet bundler

#### Default value

```YAML
jsonnet_bundler_arch: "{{ 'arm64' if ansible_architecture == 'aarch64' else 'amd64'\
  \ }}"
```

### jsonnet_bundler_download

URL to download jsonnet bundler from

#### Default value

```YAML
jsonnet_bundler_download: https://github.com/jsonnet-bundler/jsonnet-bundler/releases/download/v{{
  jsonnet_bundler_version }}/jb-linux-{{ jsonnet_bundler_arch }}
```

### jsonnet_bundler_version

Version of jsonnet bundler to install

#### Default value

```YAML
jsonnet_bundler_version: 0.5.1
```

### jsonnet_core_arch

Architecture for jsonnet binary

#### Default value

```YAML
jsonnet_core_arch: "{{ 'arm64' if ansible_architecture == 'aarch64' else 'x86_64'\
  \ }}"
```

### jsonnet_core_download

URL to download jsonnet binary from

#### Default value

```YAML
jsonnet_core_download: https://github.com/google/go-jsonnet/releases/download/v{{
  jsonnet_core_version }}/go-jsonnet_{{ jsonnet_core_version }}_Linux_{{ jsonnet_core_arch
  }}.tar.gz
```

### jsonnet_core_includes

List of binaries to include

#### Default value

```YAML
jsonnet_core_includes:
  - jsonnet
  - jsonnet-deps
  - jsonnet-lint
  - jsonnetfmt
```

### jsonnet_core_version

Version of jsonnet binary to install

#### Default value

```YAML
jsonnet_core_version: 0.20.0
```

### jsonnet_install_path

Path to install the binaries

#### Default value

```YAML
jsonnet_install_path: /usr/bin
```

## Discovered Tags

**_jsonnet_**


## Dependencies

- None

## License

Apache-2.0

## Author

[Thomas Boerger](https://github.com/tboerger)
