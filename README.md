# 🎥 Flutter PayPal Checkout

## ⚡ Best and easy way to INTEGRATE PayPal checkout in Flutter application ⚡

Main features of `flutter_paypal_checkout` : 

1. `Simple and easy to Connect Flutter with PayPal`
2. `Plug and Play🚀`
3. `Event Handlers🚀`
4. `Easy to follow guide`

## 🎖 Installing

```yaml
dependencies:
  flutter_paypal_checkout: ^<latest_version>
```

### Android
in `app\build.gradle`

```
defaultConfig {
    minSdkVersion 17
    compileSdkVersion 33    
}
```

### iOS

No extra setup is needed


## Usage

## ⚡ Setup:

```
Navigator.of(context).push(MaterialPageRoute(
    builder: (BuildContext context) => 
    
    PaypalCheckout(
        sandboxMode: true,
        clientId: "CLIENT_ID",
        secretKey: "SECRET_KEY",
        returnURL: "RETURN_URL",
        cancelURL: "CANCEL_URL",
        transactions: const [
            {
                "amount": {
                    "total": '70',
                    "currency": "USD",
                    "details": {
                        "subtotal": '70',
                        "shipping": '0',
                        "shipping_discount": 0
                    }
                },
                "description": "The payment transaction description.",
                "item_list": {
                    "items": [
                        {
                            "name": "Apple",
                            "quantity": 4,
                            "price": '5',
                            "currency": "USD"
                        },
                        {
                            "name": "Pineapple",
                            "quantity": 5,
                            "price": '10',
                            "currency": "USD"
                        }
                    ],
                    // shipping address is Optional
                    "shipping_address": {
                        "recipient_name": "Raman Singh",
                        "line1": "Delhi",
                        "line2": "",
                        "city": "Delhi",
                        "country_code": "IN",
                        "postal_code": "11001",
                        "phone": "+00000000",
                        "state": "Texas"
                    },
                }
            }
        ],
        note: "PAYMENT_NOTE",
        onSuccess: (Map params) async {
            print("onSuccess: $params");
        },
        onError: (error) {
            print("onError: $error");
            Navigator.pop(context);
        },
        onCancel: () {
            print('cancelled:');
        },
    ),

));

```
    
## ⚡ Events

```
onSuccess: (Map params) async {
    print("onSuccess: $params");
},

onError: (error) {
    print("onError: $error");
}

onCancel: () {
    print('cancelled:');
}

```

## ⚡ Constructors Parameters

| Parameter | Type | Optional | Description |
|---|---|---|---
| `sandboxMode` | bool  | YES | To use PayPal in Sandbox Mode. `Default value = false` |
| `clientId` | String | NO | Pass the PayPal Client Id. |
| `secretKey` | String | NO | Pass the PayPal Secret Key. |
| `returnURL` | String | NO | Return URL on Payment Success. |
| `cancelURL` | String | NO | Cancel URL on Payment Failed. |
| `transactions` | List\<dynamic> | NO | Transaction parameters for making payment |
| `note` | String | YES | PayPal payment note if any. |
| `onSuccess` | Function(Dynamic) | YES | Event will be called on Successful payment. |
| `onError` | Function(Dynamic) | YES | Event will be called on Error/Failed payment. |
| `onCancel` | Function(Dynamic) | YES | Event will be called on Cancelled payment. |


-----------------------------------------------------------------------------
## ⚡ Donate

> If you like my work, you can support me buying a cup of :coffee:
>
> - [PayPal](https://www.paypal.me/iSharpeners/)
> - [Patreon](https://www.patreon.com/SnippetCoder)

## Copyright & License

Code and documentation Copyright 2023 [SnippetCoder](https://www.youtube.com/SnippetCoder). Code released under the [Apache License](./LICENSE). Docs released under [Creative Commons](https://creativecommons.org/licenses/by/3.0/).