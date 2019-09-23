# Sending a Transaction

To call a smart-contract method that can change the internal state of the smart-contract you need to send a Transaction to an Orbs Node, who will then publish your Transaction under the network's consensus protocol to the Orbs network.

Transactions are made of a contract name, a method name, and a list of method arguments.

Each contract is deployed with a unique name that is used by Transaction and Query senders.

### Sending a Transaction

{% tabs %}
{% tab title="Golang" %}
```go
tx, txId, err := client.CreateTransaction(
    sender.PublicKey,  // account publicKey
    sender.PrivateKey, // account privateKey
    "contractName",    // contract name with which it was deployed
    "methodName",      // method name to call
    uint64(10),        // method arguments
    receiver.AddressAsBytes())

// send the transaction by the client
response, err := client.SendTransaction(tx)
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
const [tx, txId] = client.createTransaction(
    sender.publicKey,     // account publicKey
    sender.privateKey,    // account privateKey
    "contractName",       // contract name with which it was deployed
    "methodName",         // method name to call
    [Orbs.argUint64(10),  // method arguments
    Orbs.argAddress(receiver.address)]);
    
// send the transaction by the client
const response = await client.sendTransaction(tx);
```
{% endtab %}
{% endtabs %}

{% hint style="danger" %}
Orbs smart-contracts only support **some specific** data types. Learn more about it [here](https://docs.orbs.network/contract-sdk/orbs-contracts/data-types).
{% endhint %}

