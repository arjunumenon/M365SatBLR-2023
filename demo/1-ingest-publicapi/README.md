# Demo 1 - Ingest content from a Public API to Microsoft 365 Graph

## Summary

This is a demo repo which is insired from a [Microsoft Graph Connector sample](https://github.com/pnp/graph-connectors-samples/tree/main/samples/nodejs-javascript-solutiongallery) that shows how to ingest sample solutions from the [Microsoft 365 and Power Platform community sample gallery](https://adoption.microsoft.com/sample-solution-gallery/?keyword=&sort-by=creationDateTime-true&page=1). It gives you a very convenient way to search for and reference community samples right from your tenant!

## Prerequisites

- [Microsoft 365 Developer tenant](https://developer.microsoft.com/microsoft-365/dev-program)
- [Node@18](https://nodejs.org)
- Bash

## Steps to Execute the Sample

- Clone this repository (or [download this solution as a .ZIP file](https://pnp.github.io/download-partial/?url=https://github.com/pnp/graph-connectors-samples/tree/main/samples/nodejs-javascript-solutiongallery) then unzip it)
- Make the setup script executable, by running `chmod +x ./setup.sh`
- Run the setup script: on macOS: `./setup.sh`, on Windows `.\setup.ps1`. When finished, it will create a local `env.js` file with information about the AAD app, required to run the code
- Restore dependencies: `npm install`
- Create the external connection: `npm run createConnection` (this will take several minutes)
- Ingest the content: `npm run loadContent`

## Features

This demo shows how to ingest samples from the Microsoft 365 and Power Platform community Sample Solution Gallery into your Microsoft 365 tenant.

The demo illustrates the following concepts:

- script creating the Entra ID (Azure AD) application using CLI for Microsoft 365
- create external connection including URL to item resolver to track activity when users share external links
- create external connection schema
- retrieve data from a remote API and store it in a local cache for future use
- support incremental ingestion by tracking the last modified date of the newest sample
- ingesting items with up to 10 parallel connections to speed up the ingestion
- logging errors for easy debugging
- visualize the external content in search results using a custom Adaptive Card
- extend Microsoft Graph JavaScript SDK with a [middleware to wait for a long-running operation to complete](https://blog.mastykarz.nl/easily-handle-long-running-operations-middleware-microsoft-graph-javascript-sdk/)
- extend Microsoft Graph JavaScript SDK with a [debug middleware](https://blog.mastykarz.nl/easily-debug-microsoft-graph-javascript-sdk-requests/) to show information about outgoing requests and incoming responses

## Links and References

- [Ingest Microsoft 365 and Power Platform community samples using JavaScript and Node.js](https://github.com/pnp/graph-connectors-samples/tree/main/samples/nodejs-javascript-solutiongallery)
- Thanks to [Waldek Mastykarz](https://github.com/waldekmastykarz) who had created the original version of this sample.
