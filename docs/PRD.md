# Things 3 Integration

This document answers open questions about how the server will access data in Things 3 and which automation tools will be used.

## Automation interface

The server communicates with the local Things 3 application primarily through AppleScript. AppleScript allows reading tasks, creating new items, and triggering other advanced features that are not exposed through the URL scheme.

For simple actions like adding a to‑do or opening a specific list, the optional Things URL scheme may be used. This scheme is suitable for lightweight operations but does not provide full access to metadata.

## Authentication and security

The integration is intended to run on the same machine where Things 3 is installed. Because it is local‑only by default, no authentication is strictly required. If the server is exposed beyond localhost, an optional API token should be configured so that only authorized clients can interact with the automation scripts.
