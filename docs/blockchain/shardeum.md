

## Table of Contents

- [Introduction](#introduction)
- [Features](#features)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
- [Running the Network Locally](#running-the-network-locally)
  - [Running the JSON-RPC Server](#running-the-json-rpc-server)
- [Testing with MetaMask](#testing-with-metamask)
- [Stopping and Cleaning Up](#stopping-and-cleaning-up)
- [Health Checks](#health-checks)
- [Contributing](#contributing)
- [Community](#community)
- [License](#license)

## Introduction

Shardeum is an innovative EVM-compliant blockchain platform that leverages dynamic state sharding to achieve unprecedented scalability. By implementing a sharding model, Shardeum ensures faster processing times and lower transaction costs without compromising security or decentralization.

## Features

- **Scalability**: Horizontal scalability through sharding
- **High Performance**: Low latency and high throughput
- **Security**: Advanced cryptographic techniques and robust consensus protocols
- **Decentralization**: Truly decentralized network with no single point of failure
- **Interoperability**: EVM compatibility for existing DApps and smart contracts

## Getting Started

### Prerequisites

- Node.js (v18.16.1)
- npm (v9.5.1)
- Rust (v1.74.1)
- Docker (optional, for containerized deployment)

### Setting Up Your Environment

Shardeum requires specific versions of Nodejs, Rust and other build tools to run. 

We have detailed setup instructions [in this page](local-environment-setup.md) 

>[!IMPORTANT] 
> This is a crucial step, ensure your local environment is correctly set up before proceeding with the next steps

### Installation

1. Clone the repository:

```bash
git clone https://github.com/shardeum/shardeum.git
cd shardeum
```

2. Install dependencies:

```bash
npm ci
```

3. Network Configuration:

```bash
git apply debug-10-nodes.patch
```

Learn more about the different config options [here](local)

4. Compile project

```bash
npm run prepare
```

5. Install the Shardus CLI:

```bash
npm install -g shardus
npm update @shardus/archiver
```

## Running the Network Locally

To start a local Shardeum network with 10 nodes, run:

```bash
shardus start 10
```

### Running the JSON-RPC Server

1. Clone the JSON-RPC server repository:

```bash
git clone https://github.com/shardeum/json-rpc-server.git
cd json-rpc-server
npm install
```

2. Start the server:

```bash
npm run start
```

The default RPC URL is `http://localhost:8080`.

## Testing with MetaMask

To test your local Shardeum network using MetaMask:

1. Install the [MetaMask extension](https://metamask.io/download/).
2. Add the Shardeum network to MetaMask:

- Network Name: Shardeum
- RPC URL: http://localhost:8080
- Chain ID: 8082
- Currency Symbol: SHM
- Block Explorer URL: http://localhost:6001/

## Stopping and Cleaning Up

To stop the network and clean up resources:

```bash
shardus stop && shardus clean && rm -rf instances
```

## Health Checks
Diagnostic endpoints to check the health of the node

- GET `/is-alive` this endpoint returns 200 if the server is running.
- GET `/is-healthy` currently the same as `/is-alive` but will be expanded.

## Contributing

We welcome contributions! Please see our [Contribution Guidelines](CONTRIBUTING.md) for more information. All contributors are expected to adhere to our [Code of Conduct](CODE_OF_CONDUCT.md).

## Community

- [GitHub Discussions](https://github.com/shardeum/shardeum/discussions)
- [Discord](https://discord.com/invite/shardeum)
- [Twitter](https://twitter.com/Shardeum)

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.