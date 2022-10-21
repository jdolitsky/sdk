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
| `latest` | `sha256:295c06ffc355e81c1f0fec6cd8ca68617306939ee02e891efbe134fb1eb47395`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:295c06ffc355e81c1f0fec6cd8ca68617306939ee02e891efbe134fb1eb47395) | `amd64` `arm64` `armv7` |
| `0.0.1-r0-glibc` | `sha256:5826362c65a7177d441e8f042044a513aca748319d64ba42286b5dda0de12210`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:5826362c65a7177d441e8f042044a513aca748319d64ba42286b5dda0de12210) |  |


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
        "docker-manifest-digest": "sha256:295c06ffc355e81c1f0fec6cd8ca68617306939ee02e891efbe134fb1eb47395"
      },
      "type": "cosign container image signature"
    },
    "optional": {
      "1.3.6.1.4.1.57264.1.1": "https://token.actions.githubusercontent.com",
      "1.3.6.1.4.1.57264.1.2": "push",
      "1.3.6.1.4.1.57264.1.3": "8ebae97807dfb1bce9228aff4a3f43fdcbaf63ca",
      "1.3.6.1.4.1.57264.1.4": "Create Release",
      "1.3.6.1.4.1.57264.1.5": "chainguard-images/sdk",
      "1.3.6.1.4.1.57264.1.6": "refs/heads/main",
      "Bundle": {
        "SignedEntryTimestamp": "MEQCIEI9g3Q2J5ipGp+L2ArvD3JGSsF9LFBpJUg2PV+QSdAEAiAKL5cAJT4DqWWLblQuzTsgBqWD4lFKOaXd4OtG3voO7A==",
        "Payload": {
          "body": "eyJhcGlWZXJzaW9uIjoiMC4wLjEiLCJraW5kIjoiaGFzaGVkcmVrb3JkIiwic3BlYyI6eyJkYXRhIjp7Imhhc2giOnsiYWxnb3JpdGhtIjoic2hhMjU2IiwidmFsdWUiOiI3OWVjYjNjZTYxNTYzYTZkZjkyOTg0NDAzNTllYTY4MjlhYWE4NGFjMDllODAxNjA0MjE4NzQzMTkwNGVlZDM3In19LCJzaWduYXR1cmUiOnsiY29udGVudCI6Ik1FVUNJUUNZbi9NbG80QVdEQjFGekNjaU5XZ0ZHM3RzQzIxR3ZiNEhRU1FtMjRuMDh3SWdRV0xvQ1hOSW9ReGdMdHhzbHp1ZjN5SUFQUkMrZ3pXTjBFYkNJeXZxbFh3PSIsInB1YmxpY0tleSI6eyJjb250ZW50IjoiTFMwdExTMUNSVWRKVGlCRFJWSlVTVVpKUTBGVVJTMHRMUzB0Q2sxSlNVUnZha05EUVhsbFowRjNTVUpCWjBsVlRrVldZbVp0VWtSMk5VRlVTek5SZDFGdlJVVlRUVmxNVkVaVmQwTm5XVWxMYjFwSmVtb3dSVUYzVFhjS1RucEZWazFDVFVkQk1WVkZRMmhOVFdNeWJHNWpNMUoyWTIxVmRWcEhWakpOVWpSM1NFRlpSRlpSVVVSRmVGWjZZVmRrZW1SSE9YbGFVekZ3WW01U2JBcGpiVEZzV2tkc2FHUkhWWGRJYUdOT1RXcEplRTFFU1hkTlZHTXdUVVJKTkZkb1kwNU5ha2w0VFVSSmQwMVVZekZOUkVrMFYycEJRVTFHYTNkRmQxbElDa3R2V2tsNmFqQkRRVkZaU1V0dldrbDZhakJFUVZGalJGRm5RVVZVZUV4cGEyaFFNRVlyUWtreU1VbElNRkJFVjA1VU1WQTRRM2s0V2pWd05rc3ZTWG9LV1ZsV1RYcGlUWGRPTUV0eFZVSlFRbkJxY1UwcmVWQm9hMm96VTNZMFVTOVdMMnhCYlU1b01IaGlaWEkwYVRsaE1rdFBRMEZyV1hkblowcERUVUUwUndwQk1WVmtSSGRGUWk5M1VVVkJkMGxJWjBSQlZFSm5UbFpJVTFWRlJFUkJTMEpuWjNKQ1owVkdRbEZqUkVGNlFXUkNaMDVXU0ZFMFJVWm5VVlZPTDI1WkNrOTZVVE55YkM5VFFUazRWMmxUUlRSS00ydzNURk5KZDBoM1dVUldVakJxUWtKbmQwWnZRVlV6T1ZCd2VqRlphMFZhWWpWeFRtcHdTMFpYYVhocE5Ga0tXa1E0ZDFwUldVUldVakJTUVZGSUwwSkdjM2RYV1ZwWVlVaFNNR05JVFRaTWVUbHVZVmhTYjJSWFNYVlpNamwwVERKT2IxbFhiSFZhTTFab1kyMVJkQXBoVnpGb1dqSldla3d6VG10aGVUaDFXakpzTUdGSVZtbE1NMlIyWTIxMGJXSkhPVE5qZVRsNVdsZDRiRmxZVG14TWJteG9ZbGQ0UVdOdFZtMWplVGx2Q2xwWFJtdGplVGwwV1Zkc2RVMUVhMGREYVhOSFFWRlJRbWMzT0hkQlVVVkZTekpvTUdSSVFucFBhVGgyWkVjNWNscFhOSFZaVjA0d1lWYzVkV041Tlc0S1lWaFNiMlJYU2pGak1sWjVXVEk1ZFdSSFZuVmtRelZxWWpJd2QwVm5XVXRMZDFsQ1FrRkhSSFo2UVVKQloxRkZZMGhXZW1GRVFUSkNaMjl5UW1kRlJRcEJXVTh2VFVGRlJFSkRaelJhVjBwb1dsUnJNMDlFUVROYVIxcHBUVmRLYWxwVWEzbE5hbWhvV20xWk1GbFVUbTFPUkU1dFdrZE9hVmxYV1RKTk1rNW9DazFDZDBkRGFYTkhRVkZSUW1jM09IZEJVVkZGUkd0T2VWcFhSakJhVTBKVFdsZDRiRmxZVG14TlEwMUhRMmx6UjBGUlVVSm5OemgzUVZGVlJVWlhUbThLV1Zkc2RWb3pWbWhqYlZGMFlWY3hhRm95Vm5wTU0wNXJZWHBCWkVKbmIzSkNaMFZGUVZsUEwwMUJSVWRDUVRsNVdsZGFla3d5YUd4WlYxSjZUREl4YUFwaFZ6UjNaMWx2UjBOcGMwZEJVVkZDTVc1clEwSkJTVVZtUVZJMlFVaG5RV1JuUVVsWlNreDNTMFpNTDJGRldGSXdWM051YUVwNFJscDRhWE5HYWpORUNrOU9TblExY25kcFFtcGFkbU5uUVVGQldWQXlaVE5DZDBGQlFVVkJkMEpJVFVWVlEwbEJlRVpMTTBGSGMwcEhVbTFIVld0aFJuUlhPR2dyU1dad2Nrb0tWbkYzT0UxT1NrdFVRbmRYYTB4R1ZrRnBSVUZ6U205dmFrUkJkVXhRY1cxNUx6TlZhbkJGVjFwV1VVOTBTR1I2Y0d4dFQwaENRbWxzYkRSM0wwSkJkd3BEWjFsSlMyOWFTWHBxTUVWQmQwMUVZVkZCZDFwblNYaEJTVzFTU1hsak0yRklibEZoZUVGVU56Y3lXRkExVmpKSFoyazRTbFV2Y21KM2VGQTBOa3RtQ20xdFR6WjFXREEyZDJaWWJWUTVibnBHZWtsdE9XTlBRV05uU1hoQlNqUXlhVzl2YkUxWFJucGxRbXR5ZVc1YU5WRkVaMDVCVm1oWFMzcEhVVWhEVmtZS05FWnVOamh0ZGtoaFFYVjZZMFYzYm5SVWFrWmhiVXBZZDI1dWVtRm5QVDBLTFMwdExTMUZUa1FnUTBWU1ZFbEdTVU5CVkVVdExTMHRMUW89In19fX0=",
          "integratedTime": 1666287640,
          "logIndex": 5509712,
          "logID": "c0d23d6ad406973f9559f3ba2d1ca01f84147d8ffc5b8445c224f98b9591801d"
        }
      },
      "Issuer": "https://token.actions.githubusercontent.com",
      "Subject": "https://github.com/chainguard-images/sdk/.github/workflows/release.yaml@refs/heads/main",
      "githubWorkflowName": "Create Release",
      "githubWorkflowRef": "refs/heads/main",
      "githubWorkflowRepository": "chainguard-images/sdk",
      "githubWorkflowSha": "8ebae97807dfb1bce9228aff4a3f43fdcbaf63ca",
      "githubWorkflowTrigger": "push",
      "run_attempt": "1",
      "run_id": "3291508455",
      "sha": "8ebae97807dfb1bce9228aff4a3f43fdcbaf63ca"
    }
  }
]
```

You can verify that the image was built in Github Actions in this repository from the `Issuer` and `Subject` fields.
</details>

## Build

This image is built with [melange](https://github.com/chainguard-dev/melange) and [apko](https://github.com/chainguard-dev/apko).

