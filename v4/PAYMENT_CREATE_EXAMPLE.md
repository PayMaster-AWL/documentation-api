## Go
```go
package main

import (
	"fmt"
	"strings"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://st06.payout-master.com/api/v4/payment/create"

	payload := strings.NewReader("{\n  \"amountIn\": 500,\n  \"currency\": \"KZT\",\n  \"paymentMethod\": \"VISAMASTER\",\n  \"email\": \"support@info.com\",\n  \"lang\": \"en\",\n \"txnId\": \"en\"\n}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("PAYOUT-V4-TOKEN", "RYXwLOxxkKIYb165ZPEebSmJhO6RP1ni")
	req.Header.Add("Content-Type", "application/json")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

## NodeJs
```js
const axios = require("axios").default;

const options = {
  method: 'POST',
  url: 'https://st06.payout-master.com/api/v4/payment/create',
  headers: {'PAYOUT-V4-TOKEN': 'RYXwLOxxkKIYb165ZPEebSmJhO6RP1ni', 'Content-Type': 'application/json'},
  data: {
    amountIn: 20,
    currency: 'USD',
    paymentMethod: 'VISAMASTER',
    email: 'support@info.com',
    lang: 'en',
    txnId: '123'
  }
};

axios.request(options)
  .then(function (response) {
    console.log(response.data);
  })
  .catch(function (error) {
    console.error(error);
  });
```

## Python
```python
import requests

url = "https://st06.payout-master.com/api/v4/payment/create"

payload = {
    "amountIn": 20,
    "currency": "USD",
    "paymentMethod": "VISAMASTER",
    "email": "support@info.com",
    "lang": "en"
}
headers = {
    "PAYOUT-V4-TOKEN": "RYXwLOxxkKIYb165ZPEebSmJhO6RP1ni",
    "Content-Type": "application/json"
}

response = requests.request("POST", url, json=payload, headers=headers)

print(response.text)
```

## curl
```curl
curl -XPOST 'https://st06.payout-master.com/api/v4/payment/create' \
     -H 'PAYOUT-V4-TOKEN: RYXwLOxxkKIYb165ZPEebSmJhO6RP1ni' \
     -H 'Content-Type: application/json' \
     -d '{"amountIn":20,"currency":"USD","paymentMethod":"VISAMASTER","email":"support@info.com","lang":"en"}' \
     --compressed
```


## HTTP
```http
POST /api/v4/payment/create HTTP/1.1
PAYOUT-V4-TOKEN: RYXwLOxxkKIYb165ZPEebSmJhO6RP1ni
Content-Type: application/json
Host: https://st06.payout-master.com
Content-Length: 150

{
  "amountIn": 20,
  "currency": "USD",
  "paymentMethod": "QIWIVISAMASTER",
  "email": "support@info.com",
  "lang": "en"
}
```
