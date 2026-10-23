# Plugin organisation and test suites

This file describes the repository layout and existing test structure. The Grafana, ReviewOps and React Native to SwiftUI plugins provide implementation examples.

Installable packages live in `plugins/<plugin-name>/`. Repository companion tests live in `tests/<plugin-name>/`, with `unit/`, `integration/`, `security/` and `support/` directories where applicable. Some packages also contain deeper suites.

The root `npm run test:<plugin-name>` commands provide entry points for plugin suites, including package, functional, integration/E2E, security and language-specific checks as applicable. The marketplace dispatcher reuses these commands.

Existing plugin workflows use a master job with sequential suite, build, native-source, audit and reproducibility checks. Supported Node versions run sequentially in neighbouring plugin workflows. Shared marketplace validation is repository-wide.

CI and test documentation describe the commands and runners. Host checks, other-platform qualification and licensed-provider integration checks have different execution dependencies; skipped integration checks represent untested coverage.
