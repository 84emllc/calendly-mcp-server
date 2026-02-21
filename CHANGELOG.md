# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.0.0] - 2026-02-21

Initial public release. Fork of [meAmitPatil/calendly-mcp-server](https://github.com/meAmitPatil/calendly-mcp-server).

### Added
- Scheduling API tools: `list_event_types`, `get_event_type_availability`, `schedule_event`
- OAuth 2.0 authentication flow (authorization URL, token exchange, refresh)
- Modular tool architecture with separate tool definition files

### Upstream
- 12 tools covering OAuth, event management, and scheduling
- Personal Access Token and OAuth 2.0 authentication
- Event listing, retrieval, cancellation, and invitee management
- Organization membership listing

[1.0.0]: https://github.com/84emllc/calendly-mcp-server/releases/tag/v1.0.0
