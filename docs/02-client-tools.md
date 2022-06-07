# Installing the Client Tools

In this lab you will install the command line utilities required to complete this tutorial: [cfssl](https://github.com/cloudflare/cfssl), [cfssljson](https://github.com/cloudflare/cfssl), and [kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl).


## Install CFSSL

The `cfssl` and `cfssljson` command line utilities will be used to provision a [PKI Infrastructure](https://en.wikipedia.org/wiki/Public_key_infrastructure) and generate TLS certificates.

Download and install `cfssl` and `cfssljson` from the [cfssl repository](https://github.com/cloudflare/cfssl/releases):

### OS X

```
curl -o cfssl https://github.com/cloudflare/cfssl/releases/download/v1.6.1/cfssl_1.6.1_darwin_amd64
curl -o cfssljson https://github.com/cloudflare/cfssl/releases/download/v1.6.1/cfssljson_1.6.1_darwin_amd64
```

```
chmod +x cfssl cfssljson
```

```
sudo mv cfssl cfssljson /usr/local/bin/
```

Some OS X users may experience problems using the pre-built binaries in which case [Homebrew](https://brew.sh) might be a better option:

```
brew install cfssl
```

### Linux

```
wget -q --show-progress --https-only --timestamping \
  https://github.com/cloudflare/cfssl/releases/download/v1.6.1/cfssl_1.6.1_linux_amd64 \
  https://github.com/cloudflare/cfssl/releases/download/v1.6.1/cfssljson_1.6.1_linux_amd64
```

```
chmod +x cfssl_linux-amd64 cfssljson_linux-amd64
```

```
sudo mv cfssl_linux-amd64 /usr/local/bin/cfssl
```

```
sudo mv cfssljson_linux-amd64 /usr/local/bin/cfssljson
```

### Verification

Verify `cfssl` version 1.2.0 or higher is installed:

```
cfssl version
```

> output

```
Version: 1.6.1
Runtime: go1.17.2
```

> The cfssljson command line utility does not provide a way to print its version.

## Install kubectl

The `kubectl` command line utility is used to interact with the Kubernetes API Server. We'll use the Azure CLI to install it:

```
az aks install-cli
```

### Verification

Verify `kubectl` version 1.12.0 or higher is installed:

```
kubectl version --client
```

> output

```
Client Version: version.Info{Major:"1", Minor:"24", GitVersion:"v1.24.0", GitCommit:"4ce5a8954017644c5420bae81d72b09b735c21f0", GitTreeState:"clean", BuildDate:"2022-05-03T13:46:05Z", GoVersion:"go1.18.1", Compiler:"gc", Platform:"darwin/amd64"}
Kustomize Version: v4.5.4
```

Next: [Provisioning Compute Resources](03-compute-resources.md)
