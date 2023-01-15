#### Event schema representing when an order has been received:

```json
{
  "EventName": "order_received",
  "EventTimestamp": "YYYY-MM-DDTHH:MM:SS.SSSZ",
  "Order_id": "string",
  "Customer": {
    "Name": "Max max",
    "email": "max@email.com",
    "shippingAddress": {
      "line1": "",
      "city": "",
      "state": "",
      "postalCode": "12345"
    }
  },
  "Products": [
    {
      "product_id": "string",
      "quantity": "int"
    }
  ]
}
```

#### Event schema representing when an order has been confirmed (is not a duplicate order and can be processed):

```json
{
  "EventName": "order_confirmed",
  "EventTimestamp": "YYYY-MM-DDTHH:MM:SS.SSSZ",
  "Order_id": "string",
  "Customer": {
    "Name": "Max max",
    "email": "max@email.com",
    "shippingAddress": {
      "line1": "",
      "city": "",
      "state": "",
      "postalCode": "12345"
    }
  }
}
```

#### Event schema representing when an order has been picked from within a warehouse and packed (is ready to be shipped):

```json
{
  "EventName": "order_packed",
  "EventTimestamp": "YYYY-MM-DDTHH:MM:SS.SSSZ",
  "Order_id": "string",
  "TrackingNumber": "string",
  "Customer": {
    "Name": "Max max",
    "email": "max@email.com",
    "shippingAddress": {
      "line1": "",
      "city": "",
      "state": "",
      "postalCode": "12345"
    }
  }
}
```

#### Event schema representing when an email notification needs to be sent out:

```json
{
  "EventName": "email_notification",
  "EventTimestamp": "YYYY-MM-DDTHH:MM:SS.SSSZ",
  "RecipientEmail": "string",
  "Subject": "string",
  "Body": "string"
}
```

#### Event schema representing when a consumer is unable to successfully process an event they have received:

```json
{
  "EventName": "processing_error",
  "EventTimestamp": "YYYY-MM-DDTHH:MM:SS.SSSZ",
  "ErrorMessage": "string",
  "FailedEvent": {}
}
```
