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
| `latest` | `sha256:fbc4378942094a0374745166dfb726db5c5970116030b5573561c1982d504937`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:fbc4378942094a0374745166dfb726db5c5970116030b5573561c1982d504937) | `amd64` `arm64` `armv7` |
| `0.0.1-r0-glibc` | `sha256:e8dfb6235f663d4286cf30ce7ae27a46a79a3361a8f712bef71ddfb90bff5f3f`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:e8dfb6235f663d4286cf30ce7ae27a46a79a3361a8f712bef71ddfb90bff5f3f) |  |


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
        "docker-manifest-digest": "sha256:fbc4378942094a0374745166dfb726db5c5970116030b5573561c1982d504937"
      },
      "type": "cosign container image signature"
    },
    "optional": {
      "1.3.6.1.4.1.57264.1.1": "https://token.actions.githubusercontent.com",
      "1.3.6.1.4.1.57264.1.2": "schedule",
      "1.3.6.1.4.1.57264.1.3": "939456a8c81795121958891bc28d63d801d788e9",
      "1.3.6.1.4.1.57264.1.4": "Create Release",
      "1.3.6.1.4.1.57264.1.5": "chainguard-images/sdk",
      "1.3.6.1.4.1.57264.1.6": "refs/heads/main",
      "Bundle": {
        "SignedEntryTimestamp": "MEUCIBbjPjP2n+vAmZ2AHFUNgZCpMwbyJL8fxY3AiThbbtgqAiEA/wRdxvtZE75vcU7bZbRF57GYi21nZmUv90TZ/Pfnhu0=",
        "Payload": {
          "body": "eyJhcGlWZXJzaW9uIjoiMC4wLjEiLCJraW5kIjoiaGFzaGVkcmVrb3JkIiwic3BlYyI6eyJkYXRhIjp7Imhhc2giOnsiYWxnb3JpdGhtIjoic2hhMjU2IiwidmFsdWUiOiI3ODA2OGJkY2ZlMzhlYmU1YzU0MDFiZjcxNDc2YmM4OGFjNTZmNjY0OTM2MGZkNjJkMWRmNzk1ZGU1Mzg0NDRmIn19LCJzaWduYXR1cmUiOnsiY29udGVudCI6Ik1FVUNJQk9xTjd5SkZGUTRyTCtWdExxOW9tYi9XN3FvMXlCSHNIKzQ1dWJUc3MyZkFpRUEva1RFZXkveDZVWVZ1VkxLeGtkSDdhVHgzSS9MYW5hNS9uNStjczAyYnNVPSIsInB1YmxpY0tleSI6eyJjb250ZW50IjoiTFMwdExTMUNSVWRKVGlCRFJWSlVTVVpKUTBGVVJTMHRMUzB0Q2sxSlNVUndla05EUVhsNVowRjNTVUpCWjBsVlNESjRaRFJXTDBsNFlXUkxPVTV3U214MGJWVkdTRGx1Y1dkUmQwTm5XVWxMYjFwSmVtb3dSVUYzVFhjS1RucEZWazFDVFVkQk1WVkZRMmhOVFdNeWJHNWpNMUoyWTIxVmRWcEhWakpOVWpSM1NFRlpSRlpSVVVSRmVGWjZZVmRrZW1SSE9YbGFVekZ3WW01U2JBcGpiVEZzV2tkc2FHUkhWWGRJYUdOT1RXcEplRTFFVFhoTlJFVjRUbFJOZWxkb1kwNU5ha2w0VFVSTmVFMUVSWGxPVkUxNlYycEJRVTFHYTNkRmQxbElDa3R2V2tsNmFqQkRRVkZaU1V0dldrbDZhakJFUVZGalJGRm5RVVZRTldGWVdHSTFaMlZtWVVwRGFHMVVjbmRPUVc4MVRuZE5MMDFqU1RreVQwbzFlVFVLUVN0blpIaFNXVTV2UlRCaGFsUnhaSG81ZUhGbU9YVjBVamd3ZGpSSVZXOUtiamxUZEdvdmMxaEJjR0ZhV0ZWUWQzRlBRMEZyYzNkblowcElUVUUwUndwQk1WVmtSSGRGUWk5M1VVVkJkMGxJWjBSQlZFSm5UbFpJVTFWRlJFUkJTMEpuWjNKQ1owVkdRbEZqUkVGNlFXUkNaMDVXU0ZFMFJVWm5VVlZtVjNOMkNsTlVNR2N4WkdzNVZGZERUR2x0YnpKRmFWYzFiV1pCZDBoM1dVUldVakJxUWtKbmQwWnZRVlV6T1ZCd2VqRlphMFZhWWpWeFRtcHdTMFpYYVhocE5Ga0tXa1E0ZDFwUldVUldVakJTUVZGSUwwSkdjM2RYV1ZwWVlVaFNNR05JVFRaTWVUbHVZVmhTYjJSWFNYVlpNamwwVERKT2IxbFhiSFZhTTFab1kyMVJkQXBoVnpGb1dqSldla3d6VG10aGVUaDFXakpzTUdGSVZtbE1NMlIyWTIxMGJXSkhPVE5qZVRsNVdsZDRiRmxZVG14TWJteG9ZbGQ0UVdOdFZtMWplVGx2Q2xwWFJtdGplVGwwV1Zkc2RVMUVhMGREYVhOSFFWRlJRbWMzT0hkQlVVVkZTekpvTUdSSVFucFBhVGgyWkVjNWNscFhOSFZaVjA0d1lWYzVkV041Tlc0S1lWaFNiMlJYU2pGak1sWjVXVEk1ZFdSSFZuVmtRelZxWWpJd2QwWm5XVXRMZDFsQ1FrRkhSSFo2UVVKQloxRkpZekpPYjFwWFVqRmlSMVYzVG1kWlN3cExkMWxDUWtGSFJIWjZRVUpCZDFGdlQxUk5OVTVFVlRKWlZHaHFUMFJGTTA5VVZYaE5ha1UxVGxSbk5FOVVSbWxaZWtrMFdrUlplbHBFWjNkTlYxRXpDazlFYUd4UFZFRmpRbWR2Y2tKblJVVkJXVTh2VFVGRlJVSkJOVVJqYlZab1pFZFZaMVZ0Vm5OYVYwWjZXbFJCYWtKbmIzSkNaMFZGUVZsUEwwMUJSVVlLUWtKV2FtRkhSbkJpYldReFdWaEthMHhYYkhSWlYyUnNZM2s1ZWxwSGMzZElVVmxMUzNkWlFrSkJSMFIyZWtGQ1FtZFJVR050Vm0xamVUbHZXbGRHYXdwamVUbDBXVmRzZFUxSlIweENaMjl5UW1kRlJVRmtXalZCWjFGRFFrZ3dSV1YzUWpWQlNHTkJRMGREVXpoRGFGTXZNbWhHTUdSR2NrbzBVMk5TVjJOWkNuSkNXVGwzZW1wVFltVmhPRWxuV1RKaU0wbEJRVUZIUlVzMWRYSnNkMEZCUWtGTlFWTkVRa2RCYVVWQmFFSm1TRU5oZG5wQ1pFSnJlRGhZUkhSeVFtVUtiUzkwYW1kaWFXcFVWSEZtWVVseVJsUk9UV05HVEdORFNWRkRaV0ZOTUVwaFZXTnljMnhhV2pOdU1pOXVlbEp5TVZsRUwybFBTR1ptYURseGFrdEdRd3BrZG5jeGFVUkJTMEpuWjNGb2EycFBVRkZSUkVGM1RuQkJSRUp0UVdwRlFXMTBTVkZFYlUxdVNqQkVMM2t6UWpneFF6VkhWRlZpZUZCdlYyMU9kRGRTQ2k5ME9VcDVhRXhMWVRRek9GWmFiVkZWWTNoMFkzVm1jbGg0YWxaaVQyNDJRV3BGUVhocFR5dHVSbk5HTDNjd05XeFRRWHBQZG1KVWN6bEdhekJ0TkU0S2NGTndURVV5ZVdSS1NrVm5SMk5JVEVNdlQwUlFOa1p1UnpOM1R6WjNMMmMyUW1Wa0NpMHRMUzB0UlU1RUlFTkZVbFJKUmtsRFFWUkZMUzB0TFMwSyJ9fX19",
          "integratedTime": 1667178940,
          "logIndex": 6190903,
          "logID": "c0d23d6ad406973f9559f3ba2d1ca01f84147d8ffc5b8445c224f98b9591801d"
        }
      },
      "Issuer": "https://token.actions.githubusercontent.com",
      "Subject": "https://github.com/chainguard-images/sdk/.github/workflows/release.yaml@refs/heads/main",
      "githubWorkflowName": "Create Release",
      "githubWorkflowRef": "refs/heads/main",
      "githubWorkflowRepository": "chainguard-images/sdk",
      "githubWorkflowSha": "939456a8c81795121958891bc28d63d801d788e9",
      "githubWorkflowTrigger": "schedule",
      "run_attempt": "1",
      "run_id": "3357733091",
      "sha": "939456a8c81795121958891bc28d63d801d788e9"
    }
  }
]
```

You can verify that the image was built in Github Actions in this repository from the `Issuer` and `Subject` fields.
</details>

## Build

This image is built with [melange](https://github.com/chainguard-dev/melange) and [apko](https://github.com/chainguard-dev/apko).

