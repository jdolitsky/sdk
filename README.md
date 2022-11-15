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
| `latest` | `sha256:cda5088e106c3e408b3c28f0251c4fce48f3834c841aad25ab71239df5394abf`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:cda5088e106c3e408b3c28f0251c4fce48f3834c841aad25ab71239df5394abf) | `amd64` `arm64` `armv7` |
| `0.0.1-r0-glibc` | `sha256:73085e4942995b1da995a5e325e3911c4b3595272b10efca6bfcaf1d3cd7755d`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:73085e4942995b1da995a5e325e3911c4b3595272b10efca6bfcaf1d3cd7755d) |  |


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
        "docker-manifest-digest": "sha256:cda5088e106c3e408b3c28f0251c4fce48f3834c841aad25ab71239df5394abf"
      },
      "type": "cosign container image signature"
    },
    "optional": {
      "1.3.6.1.4.1.57264.1.1": "https://token.actions.githubusercontent.com",
      "1.3.6.1.4.1.57264.1.2": "schedule",
      "1.3.6.1.4.1.57264.1.3": "089c7b830ce0bd4de3e5a49f001be910111a7190",
      "1.3.6.1.4.1.57264.1.4": "Create Release",
      "1.3.6.1.4.1.57264.1.5": "chainguard-images/sdk",
      "1.3.6.1.4.1.57264.1.6": "refs/heads/main",
      "Bundle": {
        "SignedEntryTimestamp": "MEUCIQCT7CbKWo5INA0yp1zX/wVDSb8tGB0iMrU9hP/Ok3EUFQIgQW0nCDlv6VMBX9vhze7nY3ZF2CwWMrHm9Imp9T9BkNI=",
        "Payload": {
          "body": "eyJhcGlWZXJzaW9uIjoiMC4wLjEiLCJraW5kIjoiaGFzaGVkcmVrb3JkIiwic3BlYyI6eyJkYXRhIjp7Imhhc2giOnsiYWxnb3JpdGhtIjoic2hhMjU2IiwidmFsdWUiOiIyZWNjN2U2NzE2OTJjNDJiYmRhYjRmMzE0ZWJjMWY0NTY4MTQyNGIwYzI2NjZkY2Q4YTcxNDhlYzMxMTMwZjJhIn19LCJzaWduYXR1cmUiOnsiY29udGVudCI6Ik1FVUNJQ01DaS9QemdMcUgvR3kwYXZRMWY0bFFGVmlUellJUWh3cWxsT3BPVEdsZEFpRUF4MVB4VEpseENmM2pzc3J5K2tnTGVEc3BXM1ptc2d4QjhjNkJxbURvN280PSIsInB1YmxpY0tleSI6eyJjb250ZW50IjoiTFMwdExTMUNSVWRKVGlCRFJWSlVTVVpKUTBGVVJTMHRMUzB0Q2sxSlNVUndWRU5EUVhsMVowRjNTVUpCWjBsVlNsaFdORlJZVVRKMlNsY3JVMFJaZFdNMFIyTXJjRFZLUVdSSmQwTm5XVWxMYjFwSmVtb3dSVUYzVFhjS1RucEZWazFDVFVkQk1WVkZRMmhOVFdNeWJHNWpNMUoyWTIxVmRWcEhWakpOVWpSM1NFRlpSRlpSVVVSRmVGWjZZVmRrZW1SSE9YbGFVekZ3WW01U2JBcGpiVEZzV2tkc2FHUkhWWGRJYUdOT1RXcEplRTFVUlRCTlZFRjZUbXBSZDFkb1kwNU5ha2w0VFZSRk1FMVVRVEJPYWxGM1YycEJRVTFHYTNkRmQxbElDa3R2V2tsNmFqQkRRVkZaU1V0dldrbDZhakJFUVZGalJGRm5RVVV5ZWpBeEswTk5jMWhCTDFkaVdHcHFla1pWU0dkTGFWQkpjRlJTUlhCSFVGSTJVRmdLYUVwc2NqRjBaVlIwZFhJNU9WQXpaMGx2YUZSYU0xaG1WVU53WnpRck9GVm1RVmc0ZEZKUVRGSjNhbFV5TnpaalpuRlBRMEZyYjNkblowcEhUVUUwUndwQk1WVmtSSGRGUWk5M1VVVkJkMGxJWjBSQlZFSm5UbFpJVTFWRlJFUkJTMEpuWjNKQ1owVkdRbEZqUkVGNlFXUkNaMDVXU0ZFMFJVWm5VVlZwVkc1Q0NsVTVNRVpOYmxKNEswOWhTMnczVEZGc05XWk5WbEJSZDBoM1dVUldVakJxUWtKbmQwWnZRVlV6T1ZCd2VqRlphMFZhWWpWeFRtcHdTMFpYYVhocE5Ga0tXa1E0ZDFwUldVUldVakJTUVZGSUwwSkdjM2RYV1ZwWVlVaFNNR05JVFRaTWVUbHVZVmhTYjJSWFNYVlpNamwwVERKT2IxbFhiSFZhTTFab1kyMVJkQXBoVnpGb1dqSldla3d6VG10aGVUaDFXakpzTUdGSVZtbE1NMlIyWTIxMGJXSkhPVE5qZVRsNVdsZDRiRmxZVG14TWJteG9ZbGQ0UVdOdFZtMWplVGx2Q2xwWFJtdGplVGwwV1Zkc2RVMUVhMGREYVhOSFFWRlJRbWMzT0hkQlVVVkZTekpvTUdSSVFucFBhVGgyWkVjNWNscFhOSFZaVjA0d1lWYzVkV041Tlc0S1lWaFNiMlJYU2pGak1sWjVXVEk1ZFdSSFZuVmtRelZxWWpJd2QwWm5XVXRMZDFsQ1FrRkhSSFo2UVVKQloxRkpZekpPYjFwWFVqRmlSMVYzVG1kWlN3cExkMWxDUWtGSFJIWjZRVUpCZDFGdlRVUm5OVmw2WkdsUFJFMTNXVEpWZDFsdFVUQmFSMVY2V2xSV2FFNUViRzFOUkVGNFdXMVZOVTFVUVhoTlZFWm9DazU2UlRWTlJFRmpRbWR2Y2tKblJVVkJXVTh2VFVGRlJVSkJOVVJqYlZab1pFZFZaMVZ0Vm5OYVYwWjZXbFJCYWtKbmIzSkNaMFZGUVZsUEwwMUJSVVlLUWtKV2FtRkhSbkJpYldReFdWaEthMHhYYkhSWlYyUnNZM2s1ZWxwSGMzZElVVmxMUzNkWlFrSkJSMFIyZWtGQ1FtZFJVR050Vm0xamVUbHZXbGRHYXdwamVUbDBXVmRzZFUxSlIwdENaMjl5UW1kRlJVRmtXalZCWjFGRFFraDNSV1ZuUWpSQlNGbEJNMVF3ZDJGellraEZWRXBxUjFJMFkyMVhZek5CY1VwTENsaHlhbVZRU3pNdmFEUndlV2RET0hBM2J6UkJRVUZIUldSaVduVmFaMEZCUWtGTlFWSjZRa1pCYVVWQmNGVlVZbm8zZGxsVFNVOXRjVWg2ZW1KaVdGQUtlVUZuTUdOd1pVWjBSRE5MYTJONldrVmpOVzFsTVVGRFNVUlROR2wxYlhabGFHaEhVemxwV210bGVrVk1XbUpuZVZGWlEwSk1SQ3QwVVVkUVQxUXlSQXBDTWtKUFRVRnZSME5EY1VkVFRUUTVRa0ZOUkVFeVowRk5SMVZEVFZGRFMzcFFkbGRhU2tJNWMybDRkREpOWkZKSlZVRkVjMWw1YmpCU00zcDRhbTExQ2s1VlZXdEtNR3hKZVZneVFuZ3JPVGxaUWt0Q2NFUjRabU5MYW1JelVIZERUVU5TU0V4TmRVY3hhamRuUzIxSlFrMW9NQzg0YlN0VlRXVXlXakJ0TTJnS1RrdG5iMXByTjBSRk5tUlFORTU2YjFoeVZWUldaemd6TTFSV1lVWlZWRGRSVVQwOUNpMHRMUzB0UlU1RUlFTkZVbFJKUmtsRFFWUkZMUzB0TFMwSyJ9fX19",
          "integratedTime": 1668422215,
          "logIndex": 7048379,
          "logID": "c0d23d6ad406973f9559f3ba2d1ca01f84147d8ffc5b8445c224f98b9591801d"
        }
      },
      "Issuer": "https://token.actions.githubusercontent.com",
      "Subject": "https://github.com/chainguard-images/sdk/.github/workflows/release.yaml@refs/heads/main",
      "githubWorkflowName": "Create Release",
      "githubWorkflowRef": "refs/heads/main",
      "githubWorkflowRepository": "chainguard-images/sdk",
      "githubWorkflowSha": "089c7b830ce0bd4de3e5a49f001be910111a7190",
      "githubWorkflowTrigger": "schedule",
      "run_attempt": "3",
      "run_id": "3457610323",
      "sha": "089c7b830ce0bd4de3e5a49f001be910111a7190"
    }
  }
]
```

You can verify that the image was built in Github Actions in this repository from the `Issuer` and `Subject` fields.
</details>

## Build

This image is built with [melange](https://github.com/chainguard-dev/melange) and [apko](https://github.com/chainguard-dev/apko).

