## Introduction
Welcome to the API documentation for the Tracking service of the XIP platform, developed and maintained by AXION Company. The XIP platform offers robust and efficient logistics and tracking solutions to streamline your supply chain operations. This specific API endpoint allows you to track shipments by providing necessary details such as the type of entity (receiver or sender), CNPJ number, and NF number.

## About AXION Company
AXION Company is a leading provider of innovative logistics solutions, committed to enhancing operational efficiency and delivering superior service. To learn more about AXION Company and our suite of services, please visit https://axion.company.

## API Overview
The Tracking API is designed to provide real-time tracking information for shipments. It accepts POST requests with specific parameters and returns detailed tracking data. This documentation provides all necessary information to get started with integrating the Tracking API into your applications, including example requests in cURL, JavaScript, and Python.

## Getting Started
To start using the Tracking API, you need to send a POST request to the specified endpoint with the required headers and body parameters. The following sections provide detailed information about the request structure, including headers, body parameters, and example requests.

Feel free to explore the examples and use them to integrate the Tracking API into your system for efficient and accurate shipment tracking. If you have any questions or need further assistance, please reach out to our support team at support@axion.company.

## API Documentation for Tracking Request - XIP API

### Endpoint
POST https://xip-backend.axion.company/tracking

### Headers
`Content-Type: application/json`;

`Referer: {site_domain}`; eg.: https://www.uniaoexpress.com.br/

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
