# Deploying an Orbs smart-contract

You can also deploy a smart-contract to the Orbs network using the Client SDK. You can use this feature to test your smart-contracts and clients with the [Orbs local blockchain - Gamma](https://docs.orbs.network/contract-sdk/getting-started/installing-gamma).

{% tabs %}
{% tab title="Golang" %}
```go
// you first have to read your smart-contract code into a byte array
code := readFileAsBytes("path/to/smart-contract/file.go")

tx, txId, err := client.CreateDeployTransaction(
    sender.publicKey,  // account publicKey
    sender.privateKey, // account privateKey
    "contractName",    // contract name to deploy with
    1,                 // processor type (native)
    code)              // smart-contract code as bytes

// send the transaction by the client to deploy the contract
response, err := client.sendTransaction(tx)
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
// you first have to read your smart-contract code into a byte array
const code = readFileSync("path/to/smart-contract/file.go")

const [tx, txId] = client.createDeployTransaction(
    sener.publicKey,   // account publicKey
    sender.privateKey, // account privateKey
    "contractName",    // contract name to deploy with
    1,                 // processor type (native)
    code)              // smart-contract as bytes

// send the transaction by the client to deploy the contract
const response = await client.sendTransaction(tx)
```
{% endtab %}
{% endtabs %}

{% hint style="info" %}
In both Golang and JavaScript Client SDKs to deploy a contract with multiple files you only have to keep passing in as additional arguments to `client.createDeployTransaction` all the byte arrays of the additional files.
{% endhint %}

### A Word About Processor Types:

The Orbs Virtual Machine has an experimental feature that allows both Golang and JavaScript smart-contracts to be run. The processor type dictated whether the smart-contract is written in Golang \(`processorType = 1`\) or JavaScript \(`processorType = 2`\).

