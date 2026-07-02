```markdown
# WuKongIM Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill teaches you the core development patterns, coding conventions, and collaborative workflows used in the WuKongIM project—a Go-based instant messaging server. You'll learn how to contribute features, optimize code, update documentation, manage configuration, and maintain CI/CD pipelines, all following the repository's established practices.

## Coding Conventions

- **Language:** Go
- **Framework:** Go standard library and idiomatic Go modules

### File Naming
- Use **camelCase** for Go source files.
  - Example: `messageHandler.go`, `userSession.go`

### Import Style
- Use **relative imports** within the module.
  - Example:
    ```go
    import (
        "internal/server"
        "pkg/protocol"
    )
    ```

### Export Style
- **Mixed**: Both exported (capitalized) and unexported (lowercase) identifiers are used as appropriate.
  - Example:
    ```go
    // Exported type
    type Message struct {
        ID   string
        Body string
    }

    // Unexported helper
    func parseMessage(data []byte) (*Message, error) {
        // ...
    }
    ```

### Commit Messages
- Use **Conventional Commits**: `feat`, `fix`, `docs` prefixes.
  - Example: `feat: add message persistence`
- Average commit message length: ~19 characters.

---

## Workflows

### Update README and Docs
**Trigger:** When you want to update documentation, add diagrams, or clarify usage.  
**Command:** `/update-readme`

1. Edit `README.md`, `README_CN.md`, or `README_EN.md` as needed.
2. Optionally update or add images/diagrams in `docs/` (e.g., `.png`, `.gif`, `.pdf`, `.mdj`).
3. Commit changes with a message like `docs/update`.

**Example:**
```sh
git add README.md docs/architecture.png
git commit -m "docs/update: add architecture diagram"
git push
```

---

### Code Optimization or Refactor
**Trigger:** When you want to improve code quality, performance, or structure without adding major new features.  
**Command:** `/optimize-code`

1. Edit files across `internal/server/` and `pkg/` directories.
2. Update `go.mod` and `go.sum` if dependencies change.
3. Commit with a message like `feat: code optimization`.

**Example:**
```sh
git add internal/server/session.go pkg/protocol/codec.go go.mod go.sum
git commit -m "feat: code optimization"
git push
```

---

### Feature Development with Multi-Module Touch
**Trigger:** When you want to add a significant new capability or protocol support.  
**Command:** `/new-feature`

1. Edit or add files in `internal/server/` and `pkg/` directories.
2. Update or add tests (e.g., `*_test.go` files).
3. Optionally update `README.md` or config files.
4. Commit with a `feat:` message.

**Example:**
```sh
git add internal/server/newFeature.go pkg/protocol/new.proto pkg/protocol/newFeature_test.go
git commit -m "feat: add new protocol support"
git push
```

---

### Configuration and Deployment Update
**Trigger:** When you want to change how the app is configured or deployed.  
**Command:** `/update-config`

1. Edit `config/wk.yaml`, `docker-compose.yaml`, `Dockerfile`, or `Makefile`.
2. Optionally update related Go files (e.g., `cmd/root.go`) to support config changes.
3. Commit with `feat:` or `fix:` message.

**Example:**
```sh
git add config/wk.yaml Dockerfile
git commit -m "feat: update Dockerfile for new config"
git push
```

---

### CI/CD GitHub Actions Update
**Trigger:** When you want to change the build, release, or CI/CD process.  
**Command:** `/update-ci`

1. Edit or add files in `.github/workflows/` and/or `slsa/` directories.
2. Optionally update related documentation.
3. Commit with `update` or `feat:` message.

**Example:**
```sh
git add .github/workflows/ci.yml
git commit -m "update: add Go 1.20 to CI matrix"
git push
```

---

## Testing Patterns

- **Test File Pattern:** Files named with `.test.` or `*_test.go`.
- **Framework:** Not explicitly specified, but likely uses Go's built-in `testing` package.
- **Example Test File:**
    ```go
    // pkg/protocol/message_test.go
    package protocol

    import "testing"

    func TestMessageEncode(t *testing.T) {
        // test logic here
    }
    ```

---

## Commands

| Command         | Purpose                                               |
|-----------------|-------------------------------------------------------|
| /update-readme  | Update project documentation and diagrams             |
| /optimize-code  | Refactor or optimize code across modules              |
| /new-feature    | Add a new feature or major enhancement                |
| /update-config  | Update configuration files and deployment scripts     |
| /update-ci      | Update CI/CD workflows and GitHub Actions             |
```
