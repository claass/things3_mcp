# things3_mcp

This project aims to automate managing Tasks in Cultured Code's Things 3. The server talks to the local Things app using AppleScript. Basic actions can also be triggered through the [Things URL scheme](https://culturedcode.com/things/support/articles/2803573/) when convenient.

Authentication is optional. By default the server only listens on localhost, but an API token can be configured if remote clients need access.

For more details see [docs/PRD.md](docs/PRD.md) and Apple's [Introduction to AppleScript](https://developer.apple.com/library/archive/documentation/AppleScript/Conceptual/AppleScriptX/AppleScriptX.html).