# Payment Initialization Java Client

This is a Java client for initializing payments via the XpressPayments API. It creates a payment request payload in JSON format and sends it to the API, handling the response and any errors that occur.

## Table of Contents
- [Requirements](#requirements)
- [Setup](#setup)
- [Usage](#usage)
- [Classes Overview](#classes-overview)
  - [Metadata](#metadata)
  - [InitializePaymentRequestObject](#initializepaymentrequestobject)
  - [PaymentInitializer](#paymentinitializer)
- [Example Output](#example-output)
- [Error Handling](#error-handling)
- [License](#license)

## Requirements

- Java 8 or higher
- XpressPayments API key
- Internet connection for API requests

## Setup

1. Clone this repository or copy the code to your Java environment.
2. Replace `"Bearer XPPUBK-3c0bb71eaac24850b777cd672c223bbc-X"` with your actual API key.
3. Ensure the API URL in the code matches the endpoint URL provided by XpressPayments.

## Usage

1. Configure your `Metadata` and `InitializePaymentRequestObject` as shown in `PaymentInitializer.java`.
2. Run the program to send a payment request to the API.
3. The program will print the response from the API, or an error message if the request fails.

```java
// Main method example usage
public static void main(String[] args) {
    List<Metadata> metadataList = new ArrayList<>();
    metadataList.add(new Metadata("description", "test value"));

    InitializePaymentRequestObject paymentRequestObject = new InitializePaymentRequestObject(
            "100",
            "USERTEST1234",
            "user@example.com",
            "online",
            "NGN",
            "PROD123",
            true,
            false,
            "Test Product",
            "https://yourcallbackurl.com",
            metadataList
    );

    // Sending the request and handling the response in PaymentInitializer.java
}
