# Dependency and Release Management

This repository uses **Dependabot** and **Release Please** to automate dependency updates and version releases. These tools help us keep dependencies up to date, improve security, and reduce manual release overhead.

---

## 📦 Dependabot

**Dependabot** automatically checks for outdated or insecure dependencies and opens pull requests (PRs) with the necessary updates.

### What it does

- Opens PRs when new versions of dependencies are available.
- Checks for security vulnerabilities in dependencies.
- Can be configured to update `Dockerfile`, GitHub Actions, Go modules, Terraform modules, etc.

### Dependabot Example

Dependabot might open a PR like:

Bump actions/checkout from v3 to v4

### Configuration

Located in `.github/dependabot.yml`. You can set:
- Update frequency (daily, weekly)
- Ecosystems (e.g., `terraform`, `github-actions`, `gomod`, etc.)
- Versioning rules

---

## 🚀 Release Please

**Release Please** automates the release process by:

- Watching merged PRs for conventional commits (`feat:`, `fix:`, etc.)
- Automatically creating a release PR with a changelog update and version bump
- Creating GitHub releases with tags when the release PR is merged

### Benefits

- No need to manually update the changelog or tag versions.
- Follows semantic versioning rules based on commit messages.

### Release Please Example

If you merge a PR with:

```feat: add support for AWS S3```

### Release Please will

- Bump the minor version
- Add that feature under a `Features` section in the `CHANGELOG.md`
- Open a release PR (e.g., `chore: release v1.2.0`)
- Create a GitHub release once merged

### Configuration

Defined in `.release-please-manifest.json` and `release-please-config.json`.

---

## 🛠️ Why We're Using These Tools

- ✅ **Security**: Quick updates for vulnerable dependencies.
- ✅ **Automation**: Less manual work maintaining versions.
- ✅ **Transparency**: Clear changelogs and release history.
- ✅ **Consistency**: Enforces semantic versioning and proper release practices.

---

Let us know if you have any questions about how they work or how to write conventional commits to take advantage of these tools!
