# Starting your Client

### Initiating the Client SDK:

{% tabs %}
{% tab title="Golang" %}
```go
package main

import "github.com/orbs-network/orbs-client-sdk-go/orbs"

func main(){
    const VCHAIN_ID = 42
    client := orbs.NewClient("http://node-endpoint.com", VCHAIN_ID, codec.NETWORK_TYPE_TEST_NET)
}
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
const virtualChainId = 42;
const client = new Orbs.Client("http://node-endpoint.com", virtualChainId, Orbs.NetworkType.NETWORK_TYPE_TEST_NET);
```
{% endtab %}
{% endtabs %}

The node endpoint is the HTTP endpoint that an Orbs Node serves. You can learn more about Virtual Chain [here](https://www.orbs.com/technology/).

### Creating Orbs Accounts:

{% tabs %}
{% tab title="Golang" %}
```go
sender, err := orbs.CreateAccount()
receiver, err := orbs.CreateAccount()
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
const sender = Orbs.createAccount();
const receiver = Orbs.createAccount();
```
{% endtab %}
{% endtabs %}

{% hint style="warning" %}
This function creates a new \*random\* public-private key-pair. You can later set `privateKey` and `publicKey` to your saved key pair.

Remember to set the `address` of your account to the first 20 bytes of the SHA-256 hash of the account's `publicKey`. see [here](https://github.com/orbs-network/orbs-client-sdk-go/blob/master/orbs/account.go) for Golang or [here](https://github.com/orbs-network/orbs-client-sdk-javascript/blob/master/src/orbs/Account.ts) for JavaScript more info.
{% endhint %}



