<!-- Maintained in denissutherland52/Egrit; copy to Egrit-AI/.github/profile/README.md after review. -->

# Egrit

Last updated: 2026-11-20

**Check ARM64 containers for NVIDIA Jetson before you reach the device.**

[Egrit-Preflight](https://github.com/Egrit-AI/egrit-preflight) is a free,
open-source command line tool. On an ordinary Linux or macOS computer it
tells you whether you can run `linux/arm64` containers, what an image
declares about its architecture and Jetson dependencies, and whether a small
CPU-only ARM64 smoke test runs. It uses the Docker, Buildx and QEMU you
already have. It is not an emulator and does not install Docker, QEMU or other system dependencies.

[Get Preflight](https://github.com/Egrit-AI/egrit-preflight)
 · [Where it fits](https://github.com/Egrit-AI/egrit-preflight/blob/main/docs/where-it-fits.md)
 · [What it cannot verify](https://github.com/Egrit-AI/egrit-preflight/blob/main/docs/limitations.md)
 · [Explore Search](https://github.com/Egrit-AI/egrit-search)
 · [Connect Egrit MCP](https://github.com/Egrit-AI/egrit-search/blob/main/docs/mcp.md)
 · [Website](https://www.egrit.ai)

## Try it

```sh
egrit-preflight doctor                          # can this machine run linux/arm64 containers?
egrit-preflight image --image IMAGE_REF         # inspect an image; nothing is pulled or run
egrit-preflight smoke --image IMAGE_REF --pull --yes
egrit-preflight report --image IMAGE_REF --smoke --pull --yes -o report.json
```

Use an immutable image reference, with the digest beside the tag. Install
instructions are in the
[repository README](https://github.com/Egrit-AI/egrit-preflight#install).

## What a result means

| Outcome | Meaning |
|---|---|
| `PASS` | Checked and met. The evidence field says whether Preflight observed it or it was declared. |
| `FAIL` | Checked and not met, or refused, such as an unpinned tag. |
| `UNKNOWN` | Could not be established. Never treated as a pass. |
| `REQUIRES_HARDWARE` | Cannot be decided without a physical Jetson. |

A pass here is **not** a Jetson pass. ARM64 emulation does not provide the
Jetson GPU, the NVIDIA driver, the device nodes or the host CUDA and
TensorRT libraries. Those checks always need a physical Jetson.

## Compare against a target

Pass a small JSON target record with `--target` to compare an image with the
JetPack, CUDA and TensorRT versions you intend to run. The repository holds
[sourced examples](https://github.com/Egrit-AI/egrit-preflight/tree/main/examples/targets)
for recent JetPack releases. Each one cites NVIDIA's release page and the
date it was read, and is a declaration until read from a device.

## Free and open source

Apache-2.0, copyright 2026 Neul Space Ltd. No account, no login, no
subscription, no usage credits and no telemetry. Functionality released in
the free edition will not be withdrawn to create paid tiers.

## Beyond Preflight

Preflight stands alone. Egrit also builds related tools that are separate
and optional:

- [Search](https://github.com/Egrit-AI/egrit-search): find GPU and AI compute
  against your requirements, through the Egrit MCP.
- Plan: keep requirements, search results and Preflight reports together.
- Elevator: carry image and target context towards physical device checks.
  Device validation and deployment have separate gates.

Availability varies by tool. Check what your connection exposes: a roadmap
item is not an installed tool.

## About

Egrit is a product of Neul Space Ltd, registered in England and Wales.
NVIDIA, Jetson, JetPack, CUDA and TensorRT are trademarks of NVIDIA
Corporation. Egrit-Preflight is independent and is not an NVIDIA
certification or a statement by NVIDIA.
