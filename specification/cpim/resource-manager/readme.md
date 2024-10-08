# cpim

> see https://aka.ms/autorest

This is the AutoRest configuration file for azureadexternalidentities.

## Getting Started

To build the SDKs for My API, simply install AutoRest via `npm` (`npm install -g autorest`) and then run:

> `autorest readme.md`

To see additional help and options, run:

> `autorest --help`

For other options on installation see [Installing AutoRest](https://aka.ms/autorest/install) on the AutoRest github page.

---

## Configuration

### Basic Information

These are the global settings for the external identities APIs.

```yaml
title: ExternalIdentitiesConfigurationClient
description: External Identities Configuration Client 
openapi-type: arm
tag: package-2021-04-01
```

### Tag: package-2019-01-01-preview

These settings apply only when `--tag=package-2019-01-01-preview` is specified on the command line.

```yaml $(tag) == 'package-2019-01-01-preview'
input-file:
  - Microsoft.AzureActiveDirectory/preview/2019-01-01-preview/cpimTenant.json
```

### Tag: package-2020-05-01-preview

These settings apply only when `--tag=package-2020-05-01-preview` is specified on the command line.

```yaml $(tag) == 'package-2020-05-01-preview'
input-file:
  - Microsoft.AzureActiveDirectory/preview/2020-05-01-preview/cpim.json
```

### Tag: package-2021-04-01

These settings apply only when `--tag=package-2021-04-01` is specified on the command line.

```yaml $(tag) == 'package-2021-04-01'
input-file:
  - Microsoft.AzureActiveDirectory/stable/2021-04-01/externalIdentities.json
```


---

# Code Generation

## Swagger to SDK

This section describes what SDK should be generated by the automatic system.
This is not used by Autorest itself.

```yaml $(swagger-to-sdk)
swagger-to-sdk:
  - repo: azure-sdk-for-python-track2  
  - repo: azure-sdk-for-go
  - repo: azure-powershell
```

## Go

See configuration in [readme.go.md](./readme.go.md)

## Python

See configuration in [readme.python.md](./readme.python.md)

## CSharp

See configuration in [readme.csharp.md](./readme.csharp.md)
