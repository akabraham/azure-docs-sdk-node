---
title: Azure ManagementLock client library for JavaScript
keywords: Azure, javascript, SDK, API, @azure/arm-locks, locks
author: maggiepint
ms.author: magpint
ms.date: 07/15/2021
ms.topic: reference
ms.prod: azure
ms.technology: azure
ms.devlang: javascript
ms.service: locks
---

# Azure ManagementLock client library for JavaScript - Version 30.0.0-beta.1 


This package contains an isomorphic SDK (runs both in Node.js and in browsers) for Azure ManagementLock client.

Azure resources can be locked to prevent other users in your organization from deleting or modifying resources.

[Source code](https://github.com/Azure/azure-sdk-for-js/tree/@azure/arm-locks_30.0.0-beta.1/sdk/locks/arm-locks) |
[Package (NPM)](https://www.npmjs.com/package/@azure/arm-locks) |
[API reference documentation](https://docs.microsoft.com/javascript/api/@azure/arm-locks) |
[Samples](https://github.com/Azure-Samples/azure-samples-js-management)

## Getting started

### Currently supported environments

- [LTS versions of Node.js](https://nodejs.org/about/releases/)
- Latest versions of Safari, Chrome, Edge and Firefox.

### Prerequisites

- An [Azure subscription][azure_sub].

### Install the `@azure/arm-locks` package

Install the Azure ManagementLock client library for JavaScript with `npm`:

```bash
npm install @azure/arm-locks
```

### Create and authenticate a `ManagementLockClient`

To create a client object to access the Azure ManagementLock API, you will need the `endpoint` of your Azure ManagementLock resource and a `credential`. The Azure ManagementLock client can use Azure Active Directory credentials to authenticate.
You can find the endpoint for your Azure ManagementLock resource in the [Azure Portal][azure_portal].

#### Using an Azure Active Directory Credential

You can authenticate with Azure Active Directory using the [Azure Identity library][azure_identity]. To use the [DefaultAzureCredential][defaultazurecredential] provider shown below, or other credential providers provided with the Azure SDK, please install the `@azure/identity` package:

```bash
npm install @azure/identity
```

You will also need to register a new AAD application and grant access to Azure ManagementLock by assigning the suitable role to your service principal (note: roles such as `"Owner"` will not grant the necessary permissions).
Set the values of the client ID, tenant ID, and client secret of the AAD application as environment variables: `AZURE_CLIENT_ID`, `AZURE_TENANT_ID`, `AZURE_CLIENT_SECRET`.

```javascript
const { ManagementLockClient } = require("@azure/arm-locks");
const { DefaultAzureCredential } = require("@azure/identity");
const client = new ManagementLockClient("<endpoint>", new DefaultAzureCredential());
```

## Key concepts

### ManagementLockClient

`ManagementLockClient` is the primary interface for developers using the Azure ManagementLock client library. Explore the methods on this client object to understand the different features of the Azure ManagementLock service that you can access.

## Troubleshooting

### Logging

Enabling logging may help uncover useful information about failures. In order to see a log of HTTP requests and responses, set the `AZURE_LOG_LEVEL` environment variable to `info`. Alternatively, logging can be enabled at runtime by calling `setLogLevel` in the `@azure/logger`:

```javascript
import { setLogLevel } from "@azure/logger";
setLogLevel("info");
```

For more detailed instructions on how to enable logs, you can look at the [@azure/logger package docs](https://github.com/Azure/azure-sdk-for-js/tree/@azure/arm-locks_30.0.0-beta.1/sdk/core/logger).

## Next steps

Please take a look at the [samples](https://github.com/Azure-Samples/azure-samples-js-management) directory for detailed examples on how to use this library.

## Contributing

If you'd like to contribute to this library, please read the [contributing guide](https://github.com/Azure/azure-sdk-for-js/blob/@azure/arm-locks_30.0.0-beta.1/CONTRIBUTING.md) to learn more about how to build and test the code.

## Related projects

- [Microsoft Azure SDK for JavaScript](https://github.com/Azure/azure-sdk-for-js)

![Impressions](https://azure-sdk-impressions.azurewebsites.net/api/impressions/azure-sdk-for-js%2Fsdk%2Flocks%2Farm-locks%2FREADME.png)

[azure_cli]: https://docs.microsoft.com/cli/azure
[azure_sub]: https://azure.microsoft.com/free/
[azure_sub]: https://azure.microsoft.com/free/
[azure_portal]: https://portal.azure.com
[azure_identity]: https://github.com/Azure/azure-sdk-for-js/tree/@azure/arm-locks_30.0.0-beta.1/sdk/identity/identity
[defaultazurecredential]: https://github.com/Azure/azure-sdk-for-js/tree/@azure/arm-locks_30.0.0-beta.1/sdk/identity/identity#defaultazurecredential

