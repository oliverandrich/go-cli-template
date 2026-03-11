# Go CLI Template

[![Go Version](https://img.shields.io/badge/go-1.24-00ADD8?style=for-the-badge&logo=go&logoColor=white)](https://go.dev/)
[![License](https://img.shields.io/badge/license-EUPL--1.2-blue?style=for-the-badge)](LICENSE)
[![GitHub](https://img.shields.io/badge/github-repo-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/oliverandrich/go-cli-template)

A ready-to-use template for Go CLI applications.

## Stack

- **Go 1.24+**
- **urfave/cli v3** for argument parsing and subcommands
- **just** task runner
- **golangci-lint** for code quality
- **goreleaser** for releases

## Quick Start

```bash
# Create new project from template
gohatch github.com/oliverandrich/go-cli-template github.com/you/your-app

# Build and run
cd your-app
just build
./build/your-app
```

## Requirements

- Go 1.24+
- [gohatch](https://github.com/oliverandrich/gohatch)
- [just](https://github.com/casey/just) (command runner)
- [golangci-lint](https://golangci-lint.run/) (linting)
- [tparse](https://github.com/mfridman/tparse) (test output formatting)

## Template Variables

The template uses placeholders that gohatch replaces automatically:

| Placeholder              | Replaced with                         |
| ------------------------ | ------------------------------------- |
| `__ProjectName__`        | Binary name (last path segment)       |
| `__ProjectDescription__` | Project description (from `-d` flag)  |

## Development

```bash
just setup            # Setup project (download deps, install pre-commit hooks)
just build            # Build binary to build/<name>
just test             # Run tests
just cover            # Run tests with coverage
just cover-report     # Open coverage report in browser
just fmt              # Format code
just lint             # Run linter
just check            # Run fmt, lint, and test
just clean            # Remove build artifacts
just install          # Install to $GOPATH/bin
just release          # Create release with goreleaser
```

## Project Structure

```
├── cmd/
│   └── __ProjectName__/    # CLI entry point
│       └── main.go
├── internal/               # Internal packages
│   └── example/            # Example package
├── go.mod
├── justfile                # Task runner
├── .golangci.yml           # Linter config
└── .goreleaser.yml         # Release config
```

## License

EUPL-1.2 - see [LICENSE](LICENSE)
