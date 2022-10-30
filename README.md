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
| `latest` | `sha256:75e25dd8cabeb35509782ba2a421af2388a6b5ffaed3762236379ce9eeffd5b6`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:75e25dd8cabeb35509782ba2a421af2388a6b5ffaed3762236379ce9eeffd5b6) | `amd64` `arm64` `armv7` |
| `0.0.1-r0-glibc` | `sha256:d054204bcd0f56a28e735aadbac24965ecb5ebdba9452b7a06d9539048739ec5`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:d054204bcd0f56a28e735aadbac24965ecb5ebdba9452b7a06d9539048739ec5) |  |


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
        "docker-manifest-digest": "sha256:75e25dd8cabeb35509782ba2a421af2388a6b5ffaed3762236379ce9eeffd5b6"
      },
      "type": "cosign container image signature"
    },
    "optional": {
      "1.3.6.1.4.1.57264.1.1": "https://token.actions.githubusercontent.com",
      "1.3.6.1.4.1.57264.1.2": "schedule",
      "1.3.6.1.4.1.57264.1.3": "783c282614e34d5291b9a104ac0e9c62b2445f94",
      "1.3.6.1.4.1.57264.1.4": "Create Release",
      "1.3.6.1.4.1.57264.1.5": "chainguard-images/sdk",
      "1.3.6.1.4.1.57264.1.6": "refs/heads/main",
      "Bundle": {
        "SignedEntryTimestamp": "MEYCIQCGHUXudYg5Bznu/bnGS9pKeaVE5RGMd46LCXftipVwFAIhAP0Zl/bKF9M1Sx7J/Q2fUYQRy7tvmuiPoszwzBaUgXiu",
        "Payload": {
          "body": "eyJhcGlWZXJzaW9uIjoiMC4wLjEiLCJraW5kIjoiaGFzaGVkcmVrb3JkIiwic3BlYyI6eyJkYXRhIjp7Imhhc2giOnsiYWxnb3JpdGhtIjoic2hhMjU2IiwidmFsdWUiOiIyNDgzNTE2N2QzMWRjZWE1YmJkMmZkZjljMTVlMjI2MmUxOGI5ZGQyODNhNTc4ZTM5NjkwYzk1ODViZmY2ODMzIn19LCJzaWduYXR1cmUiOnsiY29udGVudCI6Ik1FWUNJUUNoNlM0R1NzTVhNYnFCbmVIRkxJNGVKSEVXWldXTEVJckE2aDMyb1F3MklnSWhBTVJsSWhPZXFZa3F1aFlNcUwzcTJ6QVVTcFJtTVN6bko2UmI4RkREZkpycCIsInB1YmxpY0tleSI6eyJjb250ZW50IjoiTFMwdExTMUNSVWRKVGlCRFJWSlVTVVpKUTBGVVJTMHRMUzB0Q2sxSlNVUndWRU5EUVhsNVowRjNTVUpCWjBsVlNrTm5aRXBHZUhWbllUWnJkMU5rVmpGdEwwdzNiR2RzZEZKdmQwTm5XVWxMYjFwSmVtb3dSVUYzVFhjS1RucEZWazFDVFVkQk1WVkZRMmhOVFdNeWJHNWpNMUoyWTIxVmRWcEhWakpOVWpSM1NFRlpSRlpSVVVSRmVGWjZZVmRrZW1SSE9YbGFVekZ3WW01U2JBcGpiVEZzV2tkc2FHUkhWWGRJYUdOT1RXcEplRTFFU1RWTlJFVjRUWHBCTkZkb1kwNU5ha2w0VFVSSk5VMUVSWGxOZWtFMFYycEJRVTFHYTNkRmQxbElDa3R2V2tsNmFqQkRRVkZaU1V0dldrbDZhakJFUVZGalJGRm5RVVZqVDIxT1VHZGxURVZMYkZKRmRVTldjbGRYU21ONlZGaEhZMEpSVjBORVpqRXhjamtLZFdWbFdEWnFZbGRqY1ZScWFWRXpjMmhKV2xZNFYzZFRhRlF5V1c1S2NHMDVVbXBpVjJGblp6TmtRblZxTTBzM1NUWlBRMEZyYzNkblowcElUVUUwUndwQk1WVmtSSGRGUWk5M1VVVkJkMGxJWjBSQlZFSm5UbFpJVTFWRlJFUkJTMEpuWjNKQ1owVkdRbEZqUkVGNlFXUkNaMDVXU0ZFMFJVWm5VVlV2WmxJeUNuaFBUbGcwV1dOUlQxQTFRalJRUnpWdE1HOTBPSGM0ZDBoM1dVUldVakJxUWtKbmQwWnZRVlV6T1ZCd2VqRlphMFZhWWpWeFRtcHdTMFpYYVhocE5Ga0tXa1E0ZDFwUldVUldVakJTUVZGSUwwSkdjM2RYV1ZwWVlVaFNNR05JVFRaTWVUbHVZVmhTYjJSWFNYVlpNamwwVERKT2IxbFhiSFZhTTFab1kyMVJkQXBoVnpGb1dqSldla3d6VG10aGVUaDFXakpzTUdGSVZtbE1NMlIyWTIxMGJXSkhPVE5qZVRsNVdsZDRiRmxZVG14TWJteG9ZbGQ0UVdOdFZtMWplVGx2Q2xwWFJtdGplVGwwV1Zkc2RVMUVhMGREYVhOSFFWRlJRbWMzT0hkQlVVVkZTekpvTUdSSVFucFBhVGgyWkVjNWNscFhOSFZaVjA0d1lWYzVkV041Tlc0S1lWaFNiMlJYU2pGak1sWjVXVEk1ZFdSSFZuVmtRelZxWWpJd2QwWm5XVXRMZDFsQ1FrRkhSSFo2UVVKQloxRkpZekpPYjFwWFVqRmlSMVYzVG1kWlN3cExkMWxDUWtGSFJIWjZRVUpCZDFGdlRucG5lbGw2U1RSTmFsbDRUa2RWZWs1SFVURk5hbXQ0V1dwc2FFMVVRVEJaVjAxM1dsUnNhazVxU21sTmFsRXdDazVYV1RWT1JFRmpRbWR2Y2tKblJVVkJXVTh2VFVGRlJVSkJOVVJqYlZab1pFZFZaMVZ0Vm5OYVYwWjZXbFJCYWtKbmIzSkNaMFZGUVZsUEwwMUJSVVlLUWtKV2FtRkhSbkJpYldReFdWaEthMHhYYkhSWlYyUnNZM2s1ZWxwSGMzZElVVmxMUzNkWlFrSkJSMFIyZWtGQ1FtZFJVR050Vm0xamVUbHZXbGRHYXdwamVUbDBXVmRzZFUxSlIweENaMjl5UW1kRlJVRmtXalZCWjFGRFFrZ3dSV1YzUWpWQlNHTkJRMGREVXpoRGFGTXZNbWhHTUdSR2NrbzBVMk5TVjJOWkNuSkNXVGwzZW1wVFltVmhPRWxuV1RKaU0wbEJRVUZIUlVsVmVUbGlkMEZCUWtGTlFWTkVRa2RCYVVWQmFHNXNkVkZCZVdFemNFMVJPWGMyU25wRlNUTUthMmhHYjJWTFYxSnBWR05sUkhrNE5sSllTbTR2U1RoRFNWRkRZa3hUWWxsSlZXRXljR3RuU1NzNU1WZzVORkp6Um5WVFMyTTBTMjFYTUZKaFlYSXJXQXBsTm5SUkswUkJTMEpuWjNGb2EycFBVRkZSUkVGM1RtNUJSRUpyUVdwQmJXRTVSazlqYTNod1QwOUlPRTU1U25oVWJITlVNR1Z1ZUZSNmQxaHpSSFpEQ2tWQ2VHZHJURGRuU1VwNE4xZGxjWGxZU1VzellYcGlZbVJXV0ZZdmVtTkRUVVEzYUZBMFNqSjRZMHR2VTJSR09ISXphbFZ1VEZSbFowdGlaMjlTWW1zS2RFOTJhamRKVkVGRmVuVllWemxWSzNGNlZWZDVTblpDYUcxR1IwTmxjVWsxWnowOUNpMHRMUzB0UlU1RUlFTkZVbFJKUmtsRFFWUkZMUzB0TFMwSyJ9fX19",
          "integratedTime": 1667005998,
          "logIndex": 6074132,
          "logID": "c0d23d6ad406973f9559f3ba2d1ca01f84147d8ffc5b8445c224f98b9591801d"
        }
      },
      "Issuer": "https://token.actions.githubusercontent.com",
      "Subject": "https://github.com/chainguard-images/sdk/.github/workflows/release.yaml@refs/heads/main",
      "githubWorkflowName": "Create Release",
      "githubWorkflowRef": "refs/heads/main",
      "githubWorkflowRepository": "chainguard-images/sdk",
      "githubWorkflowSha": "783c282614e34d5291b9a104ac0e9c62b2445f94",
      "githubWorkflowTrigger": "schedule",
      "run_attempt": "1",
      "run_id": "3349384595",
      "sha": "783c282614e34d5291b9a104ac0e9c62b2445f94"
    }
  }
]
```

You can verify that the image was built in Github Actions in this repository from the `Issuer` and `Subject` fields.
</details>

## Build

This image is built with [melange](https://github.com/chainguard-dev/melange) and [apko](https://github.com/chainguard-dev/apko).

