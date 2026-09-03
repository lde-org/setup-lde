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

### Install a musl build

By default the libc for Linux runners is auto-detected (glibc on GitHub-hosted runners). Override it to install the musl build instead:

```yaml
- uses: lde-org/setup-lde@v1
  with:
      libc: musl
```

## Inputs

| Input      | Description                                       | Default       |
| ---------- | ------------------------------------------------- | ------------- |
| `version`  | Version to install (`0.8.1`, `latest`, `nightly`) | `latest`      |
| `platform` | Override platform (`Linux`, `Darwin`, `Android`)  | auto-detected |
| `arch`     | Override architecture (`x86_64`, `aarch64`)       | auto-detected |
| `libc`     | Override libc for Linux (`glibc`, `musl`)         | auto-detected |

## Supported platforms

Binaries are distributed as zips and extracted to `~/.lde` (or `%USERPROFILE%\.lde` on Windows).

On Linux, `libc` selects between the glibc build (default, no suffix) and the musl build.

| `platform` | `arch`    | Asset                          |
| ---------- | --------- | ------------------------------ |
| `Linux`    | `x86_64`  | `lde-linux-x86-64.zip`         |
| `Linux`    | `x86_64`  | `lde-linux-x86-64-musl.zip`    |
| `Linux`    | `aarch64` | `lde-linux-aarch64.zip`        |
| `Linux`    | `aarch64` | `lde-linux-aarch64-musl.zip`   |
| `Android`  | `aarch64` | `lde-android-aarch64.zip`      |
| `Darwin`   | `x86_64`  | `lde-macos-x86-64.zip`         |
| `Darwin`   | `arm64`   | `lde-macos-aarch64.zip`        |
| `Windows`  | `x86_64`  | `lde-windows-x86-64.zip`       |
| `Windows`  | `aarch64` | `lde-windows-aarch64.zip`      |
