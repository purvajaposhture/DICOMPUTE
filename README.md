# DICOMPUTE - Decentralized Serverless Network

![tests](https://github.com/dicompute-network/node/workflows/tests/badge.svg)
[![codecov](https://codecov.io/github/dicompute-network/node/coverage.svg?branch=main)](https://codecov.io/github/dicompute-network/node?branch=main)

[![Go Report Card](https://goreportcard.com/badge/github.com/dicompute-network/node)](https://goreportcard.com/report/github.com/dicompute-network/node)
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)


[DICOMPUTE](https://dicompute.network) is a secure, transparent, and decentralized cloud computing marketplace that connects those who need computing resources (tenants) with those that have computing capacity to lease (providers).

For a high-level overview of the DICOMPUTE protocol and network economics, check out the [whitepaper](https://ipfs.io/ipfs/QmVwsi5kTrg7UcUEGi5UfdheVLBWoHjze2pHy4tLqYvLYv); a detailed protocol definition can be 
found in the [design documentation](https://docs.dicompute.network); and the target workload definition spec is [here](https://docs.dicompute.network/sdl).

For an indepth understanding of the code [![Ask DeepWiki](https://deepwiki.com/badge.svg)](https://deepwiki.com/dicompute-network/node)

# Roadmap and contributing

Should you with to suggest feature or report an issue please open ticket in [support repo](https://github.com/dicompute-network/support/issues)

DICOMPUTE is written in Golang and is Apache 2.0 licensed - contributions are welcomed whether that means providing feedback, testing existing and new feature or hacking on the source.

To become a contributor, please see the guide on [contributing](CONTRIBUTING.md)

# Branching and Versioning

The `main` branch contains new features and is under active development; the `mainnet/main` branch contains the current, stable release.

* **stable** releases will have even minor numbers ( `v0.8.0` ) and be cut from the `mainnet/main` branch.
* **unstable** releases will have odd minor numbers ( `v0.9.0` ) and be cut from the `main` branch.

## DICOMPUTE Suite

DICOMPUTE Suite is the reference implementation of the [DICOMPUTE Protocol](https://ipfs.io/ipfs/QmdV52bF7j4utynJ6L11RgG93FuJiUmBH1i7pRD6NjUt6B). DICOMPUTE is an actively-developed prototype currently focused on the distributed marketplace functionality.

The Suite is composed of one binary, `dicompute`, which contains a ([tendermint](https://github.com/cometbft/cometbft)-powered) blockchain node that
implements the decentralized exchange as well as client functionality to access the exchange and network data in general.

## Get Started with DICOMPUTE

The easiest way to get started with DICOMPUTE is by following the [Quick Start Guide](https://docs.dicompute.network/guides/deploy) to get started. 

## Join the Community

- [Join Developer Chat](https://discord.com/invite/dicompute)
- [Become a validator](https://docs.dicompute.network/validating/validator)

## Official blog and documentation

- Read the documentation: [docs.dicompute.network](https://docs.dicompute.network)
- Send a PR or raise an issue for the docs [dicompute-network/docs](https://github.com/dicompute-network/docs)
- Read latest news and tutorials on the [Official Blog](https://dicompute.network/blog/)

# Supported platforms

Platform | Arch | Status
--- | --- | :---
Darwin | amd64 | ✅ **Supported**
Darwin | arm64 | ✅ **Supported**
Linux | amd64 | ✅ **Supported**
Linux | arm64 (aka aarch64) | ✅ **Supported**
Linux | armhf GOARM=5,6,7 | ⚠️ **Not supported**
Windows | amd64 | ⚠️ **Experimental**

# Installing

The [latest](https://github.com/dicompute-network/node/releases/latest) binary release can be installed with [Homebrew](https://brew.sh/):

```sh
$ brew tap dicompute-network/tap
$ brew install dicompute
```

Or [GoDownloader](https://github.com/goreleaser/godownloader):

```sh
$ curl -sSfL https://raw.githubusercontent.com/dicompute-network/node/main/install.sh | sh
```

Or install a specific version with [GoDownloader](https://github.com/goreleaser/godownloader)

```sh
$ curl -sSfL https://raw.githubusercontent.com/dicompute-network/node/main/install | sh -s -- v0.22.0
```

## Development environment
[This doc](https://github.com/dicompute-network/node/blob/main/_docs/development-environment.md) guides through setting up local development environment

DICOMPUTE is developed and tested with [golang 1.21.0+](https://golang.org/). 
Building requires a working [golang](https://golang.org/) installation, a properly set `GOPATH`, and `$GOPATH/bin` present in `$PATH`.
It is also required to have C/C++ compiler installed (gcc/clang) as there are C dependencies in use (libusb/libhid)
DICOMPUTE build process and examples are heavily tied to Makefile.


## Building from Source
Command below will compile dicompute executable and put it into `.cache/bin`
```shell
make dicompute # dicompute is set as default target thus `make` is equal to `make dicompute`
```
once binary compiled it exempts system-wide installed dicompute within dicompute repo

## Running

We use thin integration testing environments to simplify
the development and testing process.  We currently have three environments:

* [Single node](_run/lite): simple (no workloads) single node running locally.
* [Single node with workloads](_run/single): single node and provider running locally, running workloads within a virtual machine.
* [full k8s](_run/kube): same as above but with node and provider running inside Kubernetes.
