# SDK.net

SDK.net is a client SDK for the Vault written in C# for .Net 7.0.
The core of the SDK is auto-generated from the Vault OpenApi document.

# Installation

1. Install dot net: https://docs.microsoft.com/en-us/dotnet/core/install/
2. Run Vault Lite.
3. Pass the URI for the Lite instance to the ClientFactory which is used to create each client.
4. From the command line run: `dotnet test`
5. The recommended IDE for .Net on MAC is https://www.jetbrains.com/help/rider/Installation_guide.html

# Repository Organization

The solution has two projects:
- Piiano: This is the SDK.
- Piiano.Tests: These are the tests that use the SDK.

## Piiano

The project contains the OpenApi specification in its root: openapi.json.
When the project is built (using `dotnet build` or `dotnet test`) it generates the file obj/GeneratedClient.cs from the specification.
The project defines clients for each of the endpoint clients. Each one is a wrapper over the generated client.
For each client, an interface can be found in the Interfaces folder and an implementation in the Implementations folder.
Currently implemented are:
- `ICollectionClient`
- `IConfVarClient`
- `IHealthClient`
- `IObjectsClient`
- `ISystemClient`
- `ITokensClient`

## Piiano.Tests

This project contains tests for each of the clients.
Currently these are organized into folders, one folder for each SDK client.
