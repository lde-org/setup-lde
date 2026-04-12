# setup-lde

A GitHub action to setup lde for your actions runners.

## Usage

```yaml
- uses: lde-org/setup-lde@v1
```

By default this will simply get the `latest` pinned release and set up `lde` in your GitHub actions PATH.

### Install a specific version

```yaml
- uses: lde-org/setup-lde@v1
  with:
      version: "0.8.1"
```

### Install nightly

```yaml
- uses: lde-org/setup-lde@v1
  with:
      version: nightly
```

### Install for a specific platform

```yaml
- uses: lde-org/setup-lde@v1
  with:
      platform: Android
      arch: aarch64
```

## Inputs

| Input      | Description                                       | Default       |
| ---------- | ------------------------------------------------- | ------------- |
| `version`  | Version to install (`0.8.1`, `latest`, `nightly`) | `latest`      |
| `platform` | Override platform (`Linux`, `Darwin`, `Android`)  | auto-detected |
| `arch`     | Override architecture (`x86_64`, `aarch64`)       | auto-detected |

## Supported platforms

| `platform` | `arch`    | Binary                  |
| ---------- | --------- | ----------------------- |
| `Linux`    | `x86_64`  | `lde-linux-x86-64`      |
| `Linux`    | `aarch64` | `lde-linux-aarch64`     |
| `Android`  | `aarch64` | `lde-android-aarch64`   |
| `Darwin`   | `x86_64`  | `lde-macos-x86-64`      |
| `Darwin`   | `arm64`   | `lde-macos-aarch64`     |
