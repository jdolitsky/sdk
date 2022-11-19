# sdk

<!---
Note: Do NOT edit directly, this file was generated using https://github.com/chainguard-images/readme-generator
-->

[![CI status](https://github.com/jdolitsky/sdk/actions/workflows/release.yaml/badge.svg)](https://github.com/jdolitsky/sdk/actions/workflows/release.yaml)

Development image for [melange](https://github.com/chainguard-dev/melange) and [apko](https://github.com/chainguard-dev/apko).

## Get It!

The image is available on `cgr.dev`:

```
docker pull cgr.dev/chainguard/sdk:latest
```

## Supported tags

| Tag | Digest | Arch |
| --- | ------ | ---- |
| `dev-alpine` `dev-alpine-20221118` | `sha256:ed43cbaa2a57c14034aec99ac48c4ea89eed8aca8bc52a1d327e33e2d2a7cad5`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:ed43cbaa2a57c14034aec99ac48c4ea89eed8aca8bc52a1d327e33e2d2a7cad5) | `amd64` `arm64` |
| `latest` | `sha256:a9d41d1b4529a79568e4c0948ea31412af528552ab60476a9061ea03db523307`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:a9d41d1b4529a79568e4c0948ea31412af528552ab60476a9061ea03db523307) | `amd64` `arm64` `armv7` |
| `0.0.1-r0-glibc` | `sha256:376fe3a1606f1257886de39623bbfe917c37badc17a8b23c77c6502e8cc51c03`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:376fe3a1606f1257886de39623bbfe917c37badc17a8b23c77c6502e8cc51c03) |  |
| `testing-20221117` | `sha256:e198df88dcb8ef760794218a309330e0b8b3c8e1dd4c211f2951f87be1f47313`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:e198df88dcb8ef760794218a309330e0b8b3c8e1dd4c211f2951f87be1f47313) | `amd64` |
| `testing` `testing-20221118` | `sha256:d6e6172257fba34e9c39e8ccd6f7292c1634357b552da0527269f3e66171c4e8`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:d6e6172257fba34e9c39e8ccd6f7292c1634357b552da0527269f3e66171c4e8) | `amd64` |
| `dev-wolfi` `dev-wolfi-20221118` | `sha256:5b49de60a54bedb10578bff89509a04cfcf44978fbe17f5c823a78741bdd6736`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:5b49de60a54bedb10578bff89509a04cfcf44978fbe17f5c823a78741bdd6736) | `amd64` |


## Usage

### With melange

Clone down your development fork/branch:

```
git clone https://github.com/chainguard-dev/melange.git
cd melange
```

Run the image, mounting the repo workspace (`--privileged` flag required):

```
docker run --privileged --rm -it -v "${PWD}:${PWD}" -w "${PWD}" cgr.dev/chainguard/sdk
```

Upon entering the image, you should see the following welcome message:

```

Welcome to the development environment!


[sdk] ❯
```

Inside the environment, test out local changes to the melange codebase
by running the following:

```
make melange install
```

Then run melange commands as normal:

```
melange keygen

melange build \
  --arch x86_64,arm64 \
  --empty-workspace \
  --repository-append packages \
  --signing-key melange.rsa \
  examples/gnu-hello.yaml
```

### With apko

Clone down your development fork/branch:

```
git clone https://github.com/chainguard-dev/apko.git
cd apko
```

Run the image, mounting the repo workspace:

```
docker run --rm -it -v "${PWD}:${PWD}" -w "${PWD}" cgr.dev/chainguard/sdk
```

Upon entering the image, you should see the following welcome message:

```

Welcome to the development environment!


[sdk] ❯
```

Inside the environment, test out local changes to the apko codebase
by running the following:

```
make apko install
```

Then run apko commands as normal:

```
apko build --debug \
  examples/alpine-base.yaml \
  alpine-base:latest output.tar
```


## Signing

All Chainguard Images are signed using [Sigstore](https://sigstore.dev)!

<details>
<br/>
To verify the image, download <a href="https://github.com/sigstore/cosign">cosign</a> and run:

```
COSIGN_EXPERIMENTAL=1 cosign verify cgr.dev/chainguard/sdk:latest | jq
```

Output:
```
Verification for cgr.dev/chainguard/sdk:latest --
The following checks were performed on each of these signatures:
  - The cosign claims were validated
  - Existence of the claims in the transparency log was verified offline
  - Any certificates were verified against the Fulcio roots.
[
  {
    "critical": {
      "identity": {
        "docker-reference": "ghcr.io/chainguard-images/sdk"
      },
      "image": {
        "docker-manifest-digest": "sha256:a9d41d1b4529a79568e4c0948ea31412af528552ab60476a9061ea03db523307"
      },
      "type": "cosign container image signature"
    },
    "optional": {
      "1.3.6.1.4.1.57264.1.1": "https://token.actions.githubusercontent.com",
      "1.3.6.1.4.1.57264.1.2": "schedule",
      "1.3.6.1.4.1.57264.1.3": "73f9f38fabde6bc189d5277dcae8fa0ab17bc8cd",
      "1.3.6.1.4.1.57264.1.4": "Create Release",
      "1.3.6.1.4.1.57264.1.5": "chainguard-images/sdk",
      "1.3.6.1.4.1.57264.1.6": "refs/heads/main",
      "Bundle": {
        "SignedEntryTimestamp": "MEYCIQCpwlJ7nSSuKdwupZxQst3W5kH/kZtvO1qtL5LI6gImlwIhAIvvUHwcnhGQJJG+Ibd2ebf454K0oe7DTWAmXEY5J+lS",
        "Payload": {
          "body": "eyJhcGlWZXJzaW9uIjoiMC4wLjEiLCJraW5kIjoiaGFzaGVkcmVrb3JkIiwic3BlYyI6eyJkYXRhIjp7Imhhc2giOnsiYWxnb3JpdGhtIjoic2hhMjU2IiwidmFsdWUiOiJlY2IxMDAwMzJiZGRkZDFlMTc0ZTI3NWZhZGZjMzZlZDM3MjRiNmJjNmM0OWEzMjRmOTRhNzRjMDY0M2MyYzdkIn19LCJzaWduYXR1cmUiOnsiY29udGVudCI6Ik1FVUNJUURUbk9DSUdkbkp3S0o5Wk9vdE96TGY2SUtNelVSWFNLcksxRG9yYTNFc3NRSWdFc002YmgvRmJiaU9VNUZRUisrZVYrUDltdGhGb2NYU1hpOWxaZG42cVVNPSIsInB1YmxpY0tleSI6eyJjb250ZW50IjoiTFMwdExTMUNSVWRKVGlCRFJWSlVTVVpKUTBGVVJTMHRMUzB0Q2sxSlNVUndha05EUVhsNVowRjNTVUpCWjBsVldraDBaV05YUTBWM00yZ3dTV3gyY2twamNGcDBTalpFV0VoUmQwTm5XVWxMYjFwSmVtb3dSVUYzVFhjS1RucEZWazFDVFVkQk1WVkZRMmhOVFdNeWJHNWpNMUoyWTIxVmRWcEhWakpOVWpSM1NFRlpSRlpSVVVSRmVGWjZZVmRrZW1SSE9YbGFVekZ3WW01U2JBcGpiVEZzV2tkc2FHUkhWWGRJYUdOT1RXcEplRTFVUlRSTlJFVjRUVlJGTUZkb1kwNU5ha2w0VFZSRk5FMUVSWGxOVkVVd1YycEJRVTFHYTNkRmQxbElDa3R2V2tsNmFqQkRRVkZaU1V0dldrbDZhakJFUVZGalJGRm5RVVZUTkd0dE5qTjVjaTl4TWpNMmRqTTNVR2hRVHpGR1R6ZEZRMmc0ZWpaeE5WQXZObFVLTURGM1RVWXdNVzAwYkhabU4wUndRalJoT1VKNVNUZ3ZTVmd4ZEV0YWFtaEVla1k1TTBWNFoyaE9VREpZWTBWTlRYRlBRMEZyYzNkblowcElUVUUwUndwQk1WVmtSSGRGUWk5M1VVVkJkMGxJWjBSQlZFSm5UbFpJVTFWRlJFUkJTMEpuWjNKQ1owVkdRbEZqUkVGNlFXUkNaMDVXU0ZFMFJVWm5VVlVyU1Rrd0NubHRLMEZTZWpRM2FrRkJiVEkzY1hBeVozQlhiekJSZDBoM1dVUldVakJxUWtKbmQwWnZRVlV6T1ZCd2VqRlphMFZhWWpWeFRtcHdTMFpYYVhocE5Ga0tXa1E0ZDFwUldVUldVakJTUVZGSUwwSkdjM2RYV1ZwWVlVaFNNR05JVFRaTWVUbHVZVmhTYjJSWFNYVlpNamwwVERKT2IxbFhiSFZhTTFab1kyMVJkQXBoVnpGb1dqSldla3d6VG10aGVUaDFXakpzTUdGSVZtbE1NMlIyWTIxMGJXSkhPVE5qZVRsNVdsZDRiRmxZVG14TWJteG9ZbGQ0UVdOdFZtMWplVGx2Q2xwWFJtdGplVGwwV1Zkc2RVMUVhMGREYVhOSFFWRlJRbWMzT0hkQlVVVkZTekpvTUdSSVFucFBhVGgyWkVjNWNscFhOSFZaVjA0d1lWYzVkV041Tlc0S1lWaFNiMlJYU2pGak1sWjVXVEk1ZFdSSFZuVmtRelZxWWpJd2QwWm5XVXRMZDFsQ1FrRkhSSFo2UVVKQloxRkpZekpPYjFwWFVqRmlSMVYzVG1kWlN3cExkMWxDUWtGSFJIWjZRVUpCZDFGdlRucE9iVTlYV1hwUFIxcG9XVzFTYkU1dFNtcE5WR2MxV2tSVmVVNTZaR3RaTWtac1QwZGFhRTFIUm1sTlZHUnBDbGw2YUdwYVJFRmpRbWR2Y2tKblJVVkJXVTh2VFVGRlJVSkJOVVJqYlZab1pFZFZaMVZ0Vm5OYVYwWjZXbFJCYWtKbmIzSkNaMFZGUVZsUEwwMUJSVVlLUWtKV2FtRkhSbkJpYldReFdWaEthMHhYYkhSWlYyUnNZM2s1ZWxwSGMzZElVVmxMUzNkWlFrSkJSMFIyZWtGQ1FtZFJVR050Vm0xamVUbHZXbGRHYXdwamVUbDBXVmRzZFUxSlIweENaMjl5UW1kRlJVRmtXalZCWjFGRFFrZ3dSV1YzUWpWQlNHTkJNMVF3ZDJGellraEZWRXBxUjFJMFkyMVhZek5CY1VwTENsaHlhbVZRU3pNdmFEUndlV2RET0hBM2J6UkJRVUZIUldsRmIzaHNRVUZCUWtGTlFWTkVRa2RCYVVWQk4ySnNWVXR3TlZWa1Z6STFhekZrU2pWbVdHc0tibEUxV1RkYU5GWmxhbTl0TjB0a1luWmtlVzVZYVZsRFNWRkVOMVJYVGl0cGVrTXhUa1ptUzNOVU9FZ3laRnBYUmpoamNWRTBjamxQZGpZNFJGWjRRUXBQWlcxb1JrUkJTMEpuWjNGb2EycFBVRkZSUkVGM1RtOUJSRUpzUVdwRlFYZG9iM1pTTUhwbk9FVTRZVEp3TWtKSWRuSnNNbVV3U0RWU1dVbHdOak5OQ21GWlRqVklSRE0zZUc1SlRtSmtkMDR5V21Oa1EzUnhhMEpvYXpCM2VHMXhRV3BCT0dkVUsxbHNhVU0zTVROUFpEUlVTQzh4VEd0R2NFTlhWbkp6VVZnS01GQm1XbVJHWW0xVlFuTnpPWGRXYVhOT1NESkhVMkZFTlhad1dFSmxSVXRQTUVrOUNpMHRMUzB0UlU1RUlFTkZVbFJKUmtsRFFWUkZMUzB0TFMwSyJ9fX19",
          "integratedTime": 1668733884,
          "logIndex": 7310771,
          "logID": "c0d23d6ad406973f9559f3ba2d1ca01f84147d8ffc5b8445c224f98b9591801d"
        }
      },
      "Issuer": "https://token.actions.githubusercontent.com",
      "Subject": "https://github.com/chainguard-images/sdk/.github/workflows/release.yaml@refs/heads/main",
      "githubWorkflowName": "Create Release",
      "githubWorkflowRef": "refs/heads/main",
      "githubWorkflowRepository": "chainguard-images/sdk",
      "githubWorkflowSha": "73f9f38fabde6bc189d5277dcae8fa0ab17bc8cd",
      "githubWorkflowTrigger": "schedule",
      "run_attempt": "1",
      "run_id": "3493171050",
      "sha": "73f9f38fabde6bc189d5277dcae8fa0ab17bc8cd"
    }
  }
]
```

You can verify that the image was built in Github Actions in this repository from the `Issuer` and `Subject` fields.
</details>

## Build

This image is built with [melange](https://github.com/chainguard-dev/melange) and [apko](https://github.com/chainguard-dev/apko).

