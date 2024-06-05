## API Documentation for Tracking Request - XIP API

### Endpoint
POST https://xip-backend.axion.company/tracking

### Headers
Content-Type: application/json
Referer: https://www.uniaoexpress.com.br/

### Request Body

| Parameter | Type | Description | Example | 
| ------------- | ------------- | ------------- | ------------- |
| type | string | Type of the entity | “receiver” or “sender” | 
| document_number | string | CNPJ number | “12.312.312/3123-12” | 
| nro_nf | string | NF number | “123” | 

### Example JSON
{
  "type": "receiver",
  "document_number": "12.312.312/3123-12",
  "nro_nf": "123"
}

### Example Requests
CURL
```bash
curl -X POST https://xip-backend.axion.company/tracking \
  -H "Content-Type: application/json" \
  -H "Referer: https://www.uniaoexpress.com.br/" \
  -d '{
    "type": "receiver",
    "document_number": "12.312.312/3123-12",
    "nro_nf": "123"
  }'
```
JavaScript (Using Fetch)
```js
const url = 'https://xip-backend.axion.company/tracking';
const data = {
  type: "receiver",
  document_number: "12.312.312/3123-12",
  nro_nf: "123"
};

const options = {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json',
    'Referer': 'https://www.uniaoexpress.com.br/'
  },
  body: JSON.stringify(data)
};

fetch(url, options)
  .then(response => response.json())
  .then(responseData => console.log(responseData))
  .catch(error => console.error('Error:', error));
```

Python (Using Requests)
```python
import requests

url = 'https://xip-backend.axion.company/tracking'
headers = {
    'Content-Type': 'application/json',
    'Referer': 'https://www.uniaoexpress.com.br/'
}
data = {
    "type": "receiver",
    "document_number": "12.312.312/3123-12",
    "nro_nf": "123"
}

response = requests.post(url, headers=headers, json=data)
print(response.json())
```

Response
The API will return a JSON object with the tracking information or an error message if the request is invalid. 
