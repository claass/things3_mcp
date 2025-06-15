
# Things 3 Integration

This document answers open questions about how the server will access data in Things 3 and which automation tools will be used.

## Automation interface

The server communicates with the local Things 3 application primarily through AppleScript. AppleScript allows reading tasks, creating new items, and triggering other advanced features that are not exposed through the URL scheme.

For simple actions like adding a to‑do or opening a specific list, the optional Things URL scheme may be used. This scheme is suitable for lightweight operations but does not provide full access to metadata.

## Authentication and security

The integration is intended to run on the same machine where Things 3 is installed. Because it is local‑only by default, no authentication is strictly required. If the server is exposed beyond localhost, an optional API token should be configured so that only authorized clients can interact with the automation scripts.
=======
# Product Requirements Document: Things3 MCP Integration

## Overview
The goal of this project is to create an MCP (Message Control Protocol) server using the [fastmcp](https://github.com/jlowin/fastmcp) Python framework that integrates with the Things 3 task management application. This server will allow external systems or clients to query, manipulate, and automate tasks stored in Things 3 through a standardized protocol.

## Goals
- Expose Things 3 data and actions through an MCP API.
- Provide a lightweight, extensible Python server implementation.
- Enable custom automation and integrations with Things 3 tasks.

## Stakeholders
- **Project Owner:** TBD
- **Development Team:** TBD
- **End Users:** People who use Things 3 and want programmatic access or automation tools.

## Assumptions
- Things 3 data is accessible from the host machine (e.g., via a database or API).
- The fastmcp framework will handle core MCP functionality, while we implement Things 3-specific handlers.

## Functional Requirements
1. **Task Listing**
   - Retrieve all tasks from Things 3.
   - Support filtering by project, tag, or status.
2. **Task Creation**
   - Add new tasks via MCP commands.
   - Support setting title, notes, due date, and other metadata.
3. **Task Updates**
   - Modify existing tasks (e.g., mark complete, change due date).
4. **Task Deletion**
   - Remove tasks or move them to Trash.
5. **Authentication/Authorization**
   - Optionally secure endpoints with API keys or tokens.
6. **Extensibility**
   - Provide a plugin interface for additional commands or integrations.

## Non-Functional Requirements
- **Performance:** Handle requests with minimal latency for local or LAN environments.
- **Reliability:** Ensure the server remains stable even if Things 3 data is large.
- **Maintainability:** Follow clear, documented code structure with tests.

## Milestones
1. **Project Setup**
   - Initialize Python environment and fastmcp dependency.
   - Define basic server structure.
2. **Things 3 Access Layer**
   - Implement functions to read/write tasks from Things 3.
3. **Core MCP Commands**
   - Implement listing, creation, update, and deletion commands.
   - Add basic authentication if required.
4. **Testing & Documentation**
   - Write unit tests for MCP command handlers.
   - Document API usage and examples.
5. **Deployment**
   - Provide instructions for running the server locally or on a home server.

## Success Metrics
- Ability to list, create, update, and delete tasks in Things 3 via MCP commands.
- Automated test suite achieves high coverage for command handlers.
- Documentation allows new developers to understand and extend the server easily.

## Out of Scope
- Building a full-fledged GUI for Things 3 management.
- Direct cloud hosting or scaling considerations.

## Open Questions
- How will Things 3 data be accessed on the host machine? (API vs. direct database)
- What authentication mechanism should the server use, if any?
- Are there existing Things 3 automation tools we can leverage?

