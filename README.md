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
| `dev-alpine-20221123` | `sha256:abc19835b5c35dff2d33041da5e30846598601eb4bc05d86fdc17651c4016538`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:abc19835b5c35dff2d33041da5e30846598601eb4bc05d86fdc17651c4016538) | `amd64` `arm64` |
| `dev-wolfi-20221127` | `sha256:4e9860f39572e938853ef8987aa0f02bf2508dd0999a4c708c32b8863bfd8eec`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:4e9860f39572e938853ef8987aa0f02bf2508dd0999a4c708c32b8863bfd8eec) | `amd64` |
| `0.0.1-r0-glibc` | `sha256:bfcd049a213dbab7fd1b33d7e527503883ad24cba9ea17a83b7cd638b037242b`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:bfcd049a213dbab7fd1b33d7e527503883ad24cba9ea17a83b7cd638b037242b) |  |
| `testing-20221117` | `sha256:e198df88dcb8ef760794218a309330e0b8b3c8e1dd4c211f2951f87be1f47313`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:e198df88dcb8ef760794218a309330e0b8b3c8e1dd4c211f2951f87be1f47313) | `amd64` |
| `dev-wolfi` `dev-wolfi-20221128` | `sha256:a5169cc2508f1d3d8112fb64fe1b999f33d5db8ba300105e4157018cad7c3125`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:a5169cc2508f1d3d8112fb64fe1b999f33d5db8ba300105e4157018cad7c3125) | `amd64` |
| `dev-alpine` `dev-alpine-20221127` | `sha256:0529690fec0263afd03035eff82e840cb28d00b2a200f7aab001c6b3b81f02ab`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:0529690fec0263afd03035eff82e840cb28d00b2a200f7aab001c6b3b81f02ab) | `amd64` `arm64` |
| `dev-wolfi-20221119` | `sha256:aefddde028e9c3d271e7a3254cd917eb249581d3a76d1fade132243a9ebe0027`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:aefddde028e9c3d271e7a3254cd917eb249581d3a76d1fade132243a9ebe0027) | `amd64` |
| `dev-alpine-20221124` | `sha256:7203b3719a18f626a2efea1a552fce545bd4f537f63edce9d70e509fdb44f053`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:7203b3719a18f626a2efea1a552fce545bd4f537f63edce9d70e509fdb44f053) | `amd64` `arm64` |
| `latest` | `sha256:fa99310074c4993783e6460c7d09126b64cc4a26cbcf94afd36ab9d67d79a0fc`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:fa99310074c4993783e6460c7d09126b64cc4a26cbcf94afd36ab9d67d79a0fc) | `amd64` `arm64` `armv7` |
| `dev-wolfi-20221118` | `sha256:5b49de60a54bedb10578bff89509a04cfcf44978fbe17f5c823a78741bdd6736`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:5b49de60a54bedb10578bff89509a04cfcf44978fbe17f5c823a78741bdd6736) | `amd64` |
| `dev-alpine-20221119` | `sha256:8aabbaf50bf153583a523e5ff0db915fa232208a4791fa8fbd16005ba80b4157`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:8aabbaf50bf153583a523e5ff0db915fa232208a4791fa8fbd16005ba80b4157) | `amd64` `arm64` |
| `dev-wolfi-20221120` | `sha256:5475c40123a6ebbfd4aab4fa77ab7a3f7189e8084c9bd59c718ac8a585afc21e`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:5475c40123a6ebbfd4aab4fa77ab7a3f7189e8084c9bd59c718ac8a585afc21e) | `amd64` |
| `dev-wolfi-20221123` | `sha256:69adc4d96dc34877f831af12f04d752acc4869a0853530736864138227efd377`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:69adc4d96dc34877f831af12f04d752acc4869a0853530736864138227efd377) | `amd64` |
| `dev-wolfi-20221125` | `sha256:65b371411fae5350b91f65c8c831e6bb35699862f6d8dcbab7ea71511b12a182`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:65b371411fae5350b91f65c8c831e6bb35699862f6d8dcbab7ea71511b12a182) | `amd64` |
| `dev-alpine-20221120` | `sha256:4c806210640ffce120e92d6b708c48b5fc90a347536ebc671f4a0122bf7ebfca`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:4c806210640ffce120e92d6b708c48b5fc90a347536ebc671f4a0122bf7ebfca) | `amd64` `arm64` |
| `dev-wolfi-20221121` | `sha256:94a61c7857febefef01c12f364bcc582296d1b39b3ac1fba84a3b908cf0607f2`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:94a61c7857febefef01c12f364bcc582296d1b39b3ac1fba84a3b908cf0607f2) | `amd64` |
| `dev-alpine-20221121` | `sha256:d17b5535920b7ee245c51f3d0f5d4317e925ad3bc6ac731c47956df0ba2fb9a4`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:d17b5535920b7ee245c51f3d0f5d4317e925ad3bc6ac731c47956df0ba2fb9a4) | `amd64` `arm64` |
| `dev-wolfi-20221122` | `sha256:ef2dc5677acae79e49be72cc0241cd7329dcf7b369ce645e35cdc8f356f9aeee`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:ef2dc5677acae79e49be72cc0241cd7329dcf7b369ce645e35cdc8f356f9aeee) | `amd64` |
| `dev-alpine-20221122` | `sha256:130d2accbfe32c4a83a20ec0632661834b4ee732715f3ffa33f72ab3dd5080c4`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:130d2accbfe32c4a83a20ec0632661834b4ee732715f3ffa33f72ab3dd5080c4) | `amd64` `arm64` |
| `dev-alpine-20221126` | `sha256:3708f8cc667fb4eb3f5bb4b2dd15e3da0286e6dc440b72fcaa4f3f46b1b3c729`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:3708f8cc667fb4eb3f5bb4b2dd15e3da0286e6dc440b72fcaa4f3f46b1b3c729) | `amd64` `arm64` |
| `testing` `testing-20221118` | `sha256:d6e6172257fba34e9c39e8ccd6f7292c1634357b552da0527269f3e66171c4e8`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:d6e6172257fba34e9c39e8ccd6f7292c1634357b552da0527269f3e66171c4e8) | `amd64` |
| `dev-alpine-20221118` | `sha256:ed43cbaa2a57c14034aec99ac48c4ea89eed8aca8bc52a1d327e33e2d2a7cad5`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:ed43cbaa2a57c14034aec99ac48c4ea89eed8aca8bc52a1d327e33e2d2a7cad5) | `amd64` `arm64` |
| `dev-wolfi-20221124` | `sha256:2d836578c7c624eb1257f482ef6ec581285c965af2ac644b3cb3f1ea00d05264`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:2d836578c7c624eb1257f482ef6ec581285c965af2ac644b3cb3f1ea00d05264) | `amd64` |
| `dev-alpine-20221125` | `sha256:3633ae4ec4f28b15fa084e9e7f684197c021f0ee58a91736f30167fbff9bee11`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:3633ae4ec4f28b15fa084e9e7f684197c021f0ee58a91736f30167fbff9bee11) | `amd64` `arm64` |
| `dev-wolfi-20221126` | `sha256:aa430f502c3d91198f0a2ac23d5e8956c10ada8c79498c81772bdff34a729013`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:aa430f502c3d91198f0a2ac23d5e8956c10ada8c79498c81772bdff34a729013) | `amd64` |


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
        "docker-manifest-digest": "sha256:fa99310074c4993783e6460c7d09126b64cc4a26cbcf94afd36ab9d67d79a0fc"
      },
      "type": "cosign container image signature"
    },
    "optional": {
      "1.3.6.1.4.1.57264.1.1": "https://token.actions.githubusercontent.com",
      "1.3.6.1.4.1.57264.1.2": "schedule",
      "1.3.6.1.4.1.57264.1.3": "891a2a35afc9f8b1bfbb03bbaa1d34233f9631a6",
      "1.3.6.1.4.1.57264.1.4": "Create Release",
      "1.3.6.1.4.1.57264.1.5": "chainguard-images/sdk",
      "1.3.6.1.4.1.57264.1.6": "refs/heads/main",
      "Bundle": {
        "SignedEntryTimestamp": "MEUCIQDgkTpdECPhNuWfwah7imFHR77+zerez/pTxj5TTtrP6AIgbHE2voDLrQEfQWT3pXYk3efku1kVRlGj+EWL1qHllu8=",
        "Payload": {
          "body": "eyJhcGlWZXJzaW9uIjoiMC4wLjEiLCJraW5kIjoiaGFzaGVkcmVrb3JkIiwic3BlYyI6eyJkYXRhIjp7Imhhc2giOnsiYWxnb3JpdGhtIjoic2hhMjU2IiwidmFsdWUiOiIwNDFmOGQzNmRhNjhkNDc5NzE5M2ZhMGY3MzAwMjM1ODg1MWIzZDNlY2FkNjA2OTFjYjliNjNhYmQ3ZjY0OWI0In19LCJzaWduYXR1cmUiOnsiY29udGVudCI6Ik1FVUNJQWNBNEwxT0s3aWExZWhWWWtHRWEyTmloSHR1UDZkZVN2dWx6YllFUGR0ZUFpRUE3Q3pPNDZIckV6N1JVMUdzc0cyMDBOVXJ0VjNRWTZQTmhWSGcyS3ZKbURjPSIsInB1YmxpY0tleSI6eyJjb250ZW50IjoiTFMwdExTMUNSVWRKVGlCRFJWSlVTVVpKUTBGVVJTMHRMUzB0Q2sxSlNVUndha05EUVhsNVowRjNTVUpCWjBsVlMyTTFUVzF1Wm1wS1pFZG9OV0pXZGpnNGFXVnJiVTgwZDBaUmQwTm5XVWxMYjFwSmVtb3dSVUYzVFhjS1RucEZWazFDVFVkQk1WVkZRMmhOVFdNeWJHNWpNMUoyWTIxVmRWcEhWakpOVWpSM1NFRlpSRlpSVVVSRmVGWjZZVmRrZW1SSE9YbGFVekZ3WW01U2JBcGpiVEZzV2tkc2FHUkhWWGRJYUdOT1RXcEplRTFVU1ROTlJFRXdUbnBKZUZkb1kwNU5ha2w0VFZSSk0wMUVRVEZPZWtsNFYycEJRVTFHYTNkRmQxbElDa3R2V2tsNmFqQkRRVkZaU1V0dldrbDZhakJFUVZGalJGRm5RVVUzTVRGdFZHOXFXRU5JTW5WRGF6TjZTVXBhZDBOTlVsVlNVRTFEZDNSVlZGWkpOMlFLUmtSNFdWVjJlbmRaU0ZVdlprZE5TVlpMWTB0a1RVa3JLMnBOT1ZCNlNqUm9VbFpFVVhGNWRWaENZa0pIVTBkb2J6WlBRMEZyYzNkblowcElUVUUwUndwQk1WVmtSSGRGUWk5M1VVVkJkMGxJWjBSQlZFSm5UbFpJVTFWRlJFUkJTMEpuWjNKQ1owVkdRbEZqUkVGNlFXUkNaMDVXU0ZFMFJVWm5VVlZGY1RoVENtVm5TbEJVYUVOcmRFbHpOWE5SUjFCWlRHUm9hSFpGZDBoM1dVUldVakJxUWtKbmQwWnZRVlV6T1ZCd2VqRlphMFZhWWpWeFRtcHdTMFpYYVhocE5Ga0tXa1E0ZDFwUldVUldVakJTUVZGSUwwSkdjM2RYV1ZwWVlVaFNNR05JVFRaTWVUbHVZVmhTYjJSWFNYVlpNamwwVERKT2IxbFhiSFZhTTFab1kyMVJkQXBoVnpGb1dqSldla3d6VG10aGVUaDFXakpzTUdGSVZtbE1NMlIyWTIxMGJXSkhPVE5qZVRsNVdsZDRiRmxZVG14TWJteG9ZbGQ0UVdOdFZtMWplVGx2Q2xwWFJtdGplVGwwV1Zkc2RVMUVhMGREYVhOSFFWRlJRbWMzT0hkQlVVVkZTekpvTUdSSVFucFBhVGgyWkVjNWNscFhOSFZaVjA0d1lWYzVkV041Tlc0S1lWaFNiMlJYU2pGak1sWjVXVEk1ZFdSSFZuVmtRelZxWWpJd2QwWm5XVXRMZDFsQ1FrRkhSSFo2UVVKQloxRkpZekpPYjFwWFVqRmlSMVYzVG1kWlN3cExkMWxDUWtGSFJIWjZRVUpCZDFGdlQwUnJlRmxVU21oTmVsWm9XbTFOTlZwcWFHbE5WMHB0V1cxSmQwMHlTbWxaVjBWNFdrUk5NRTFxVFhwYWFtc3lDazE2Um1oT2FrRmpRbWR2Y2tKblJVVkJXVTh2VFVGRlJVSkJOVVJqYlZab1pFZFZaMVZ0Vm5OYVYwWjZXbFJCYWtKbmIzSkNaMFZGUVZsUEwwMUJSVVlLUWtKV2FtRkhSbkJpYldReFdWaEthMHhYYkhSWlYyUnNZM2s1ZWxwSGMzZElVVmxMUzNkWlFrSkJSMFIyZWtGQ1FtZFJVR050Vm0xamVUbHZXbGRHYXdwamVUbDBXVmRzZFUxSlIweENaMjl5UW1kRlJVRmtXalZCWjFGRFFrZ3dSV1YzUWpWQlNHTkJNMVF3ZDJGellraEZWRXBxUjFJMFkyMVhZek5CY1VwTENsaHlhbVZRU3pNdmFEUndlV2RET0hBM2J6UkJRVUZIUlhSdk1sSlVVVUZCUWtGTlFWTkVRa2RCYVVWQmFXcHFWblJYTWs1bWNreG9aMkZTVFUxYVVYb0tXbXNyWkZwblRsRmFNMUJNYURGd2IyeGtZMjVSZWtGRFNWRkRSMHBZYkZOTU56aEROelZ0YXpoT1lreEVPVFJoY0VsTFF6VlRVVmgxYzBkcVZWaG1TUXAwYUc5UVZucEJTMEpuWjNGb2EycFBVRkZSUkVGM1RtOUJSRUpzUVdwRlFUSjBWVXMxVkcxUFVWcFJWbkJEVmtKaWVVRkVVbFowUm14WlZGazRMMnBZQ21jNU0wNW1PRk5CVDJ4RFpGSldjek51U21kR1QyZ3hjSHBHUkV0dldFRTBRV3BDUTNNeVFXbHZlblZoVFhsc1FtRTBlWEp4ZEhWWE5HaEhjMU5TTWtzS2EyOW9ORGgwYTFndkwwaG5kREI2WjBWWGJVOXZkR2hYZDBwSk1Yb3hiRmQwVWxFOUNpMHRMUzB0UlU1RUlFTkZVbFJKUmtsRFFWUkZMUzB0TFMwSyJ9fX19",
          "integratedTime": 1669510049,
          "logIndex": 7919258,
          "logID": "c0d23d6ad406973f9559f3ba2d1ca01f84147d8ffc5b8445c224f98b9591801d"
        }
      },
      "Issuer": "https://token.actions.githubusercontent.com",
      "Subject": "https://github.com/chainguard-images/sdk/.github/workflows/release.yaml@refs/heads/main",
      "githubWorkflowName": "Create Release",
      "githubWorkflowRef": "refs/heads/main",
      "githubWorkflowRepository": "chainguard-images/sdk",
      "githubWorkflowSha": "891a2a35afc9f8b1bfbb03bbaa1d34233f9631a6",
      "githubWorkflowTrigger": "schedule",
      "run_attempt": "1",
      "run_id": "3555897829",
      "sha": "891a2a35afc9f8b1bfbb03bbaa1d34233f9631a6"
    }
  }
]
```

You can verify that the image was built in Github Actions in this repository from the `Issuer` and `Subject` fields.
</details>

## Build

This image is built with [melange](https://github.com/chainguard-dev/melange) and [apko](https://github.com/chainguard-dev/apko).

