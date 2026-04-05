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

## Inputs

| Input     | Description                                       | Default  |
| --------- | ------------------------------------------------- | -------- |
| `version` | Version to install (`0.8.1`, `latest`, `nightly`) | `latest` |
