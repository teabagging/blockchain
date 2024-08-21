

## Overview

**Tachyon** is a Modular ZK Backend, powered by GPU.

## Join Our Developer Community

We're thrilled to have you become a part of our community!

If your passion for Tachyon matches ours, we extend a warm invitation for you to join our developer community on [Telegram](https://t.me/zktachyon). Ask questions, share insights, or simply stay informed on Tachyon's newest updates with other developers and the original team through our Telegram group. We hope to see you there!

Thank you for your keen interest in contributing to Tachyon! ✨

## Design Goals

1. General Purpose: A versatile ZK library empowers developers to implement any proving scheme with minimal effort, often enhancing developer productivity. To create a general-purpose backend, aligning the code structure as closely as possible with the algebraic structure is paramount.
2. Easy to Use: Achieving widespread adoption is essential for the success of any product. Consequently, one of the key focal points of the Tachyon project is to include offering packages for various programming languages and runtimes.
3. Blazing Fast: Tachyon's foremost requirement is speed, and not just any speed, but blazing speed! This entails Tachyon delivering exceptional performance on both CPU and GPU platforms.
4. GPU Interoperability: Tachyon's code is designed to be compatible with both CPU and GPU in the majority of scenarios.

## List of Features

Symbol Definitions:

- :heavy_check_mark: Currently supported.
- 🏗️ Partially implemented or is under active construction.
- :x: Not currently supported.

### Finite Fields

|              | CPU                | GPU                |
| ------------ | ------------------ | ------------------ |
| BabyBear     | :heavy_check_mark: | :heavy_check_mark: |
| BinaryFields | :heavy_check_mark: | :heavy_check_mark: |
| Goldilocks   | :heavy_check_mark: | :heavy_check_mark: |
| Mersenne-31  | :heavy_check_mark: | :heavy_check_mark: |
| KoalaBear    | :heavy_check_mark: | :heavy_check_mark: |

### Elliptic Curves

|           | CPU                | GPU                |
| --------- | ------------------ | ------------------ |
| BN254     | :heavy_check_mark: | :heavy_check_mark: |
| BLS12-381 | :heavy_check_mark: | :heavy_check_mark: |
| Secp256k1 | :heavy_check_mark: | :heavy_check_mark: |
| Pallas    | :heavy_check_mark: | :heavy_check_mark: |
| Vesta     | :heavy_check_mark: | :heavy_check_mark: |

### Commitment Schemes

|          | CPU                | GPU                |
| -------- | ------------------ | ------------------ |
| GWC      | :heavy_check_mark: | :heavy_check_mark: |
| SHPlonk  | :heavy_check_mark: | :heavy_check_mark: |
| FRI      | :heavy_check_mark: | :x:                |
| Pedersen | :heavy_check_mark: | :heavy_check_mark: |

### Hashes

|           | CPU                | GPU |
| --------- | ------------------ | --- |
| Poseidon  | :heavy_check_mark: | :x: |
| Poseidon2 | :heavy_check_mark: | :x: |

### FFT

|               | CPU                | GPU                |
| ------------- | ------------------ | ------------------ |
| Radix2FFT     | :heavy_check_mark: | :heavy_check_mark: |
| MixedRadixFFT | :heavy_check_mark: | :heavy_check_mark: |

### Lookups

|       | CPU                | GPU |
| ----- | ------------------ | --- |
| Halo2 | :heavy_check_mark: | :x: |

### SNARKs

|         | CPU                | GPU                |
| ------- | ------------------ | ------------------ |
| Groth16 | :heavy_check_mark: | :heavy_check_mark: |
| Halo2   | :heavy_check_mark: | :x:                |

### Frontends

|                 | CPU                | GPU                |
| --------------- | ------------------ | ------------------ |
| Circom(groth16) | :heavy_check_mark: | :heavy_check_mark: |
| Halo2           | :heavy_check_mark: | :x:                |

## Roadmap

- [x] 2024Q1 - Enable producing the [zkEVM](https://github.com/kroma-network/zkevm-circuits) proof.
- [x] 2024Q2 - Replace Halo2 with Tachyon in [Kroma](https://kroma.network/) mainnet.
- [ ] 2024Q3a - Implement and optimize Plonky3 in Tachyon.
- [ ] 2024Q3b - Replace zkEVM with [SP1](https://github.com/succinctlabs/sp1) zkVM in [Kroma](https://kroma.network/) mainnet.

## Prerequisites

### Bazel

Please follow the instructions [here](https://bazel.build/install).

### Ubuntu

```shell
sudo apt install libgmp-dev libomp-dev
```

### Macos

```shell
brew install gmp libomp
```

## Getting started

### Build

```shell
bazel build --config {os} //...
```

### Test

```shell
bazel test --config {os} //...
```

Check [How To Build](/docs/how_to_use/how_to_build.md) for more information.
