# Sending a Query

To call a smart-contract method that does not alter the internal state of the smart-contract you need to send a Query to and Orbs Node, who will only read it's smart-contract state. This execution model does not undergo any consensus protocol because the Orbs blockchain state is not changed.

Queries are made of a contract name, a method name, and a list of method arguments.

Each contract is deployed with a unique name that is used by Transaction and Query senders.

{% tabs %}
{% tab title="Golang" %}
```go
query, err = client.CreateQuery(
    receiver.PublicKey,        // account publicKey
    "contractName",            // contract name with which it was deployed
    "methodName",              // method name to call
    receiver.AddressAsBytes()) // method arguments
    
// send the query by the client
response, err := client.SendQuery(query)
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
const query = client.createQuery(
    receiver.publicKey,                   // account publicKey
    "contractName",                       // contract name with which it was deployed
    "methodName",                         // method name to call
    [Orbs.argAddress(receiver.address)]); // method arguments

// send the query by the client
const response = await client.sendQuery(query);
```
{% endtab %}
{% endtabs %}

{% hint style="info" %}
Orbs smart-contracts only support **some specific** data types. Learn more about it [here](https://docs.orbs.network/contract-sdk/orbs-contracts/data-types).
{% endhint %}

