# Orange Money API

A Node.js wrapper for the Orange Money Web Payment API.

## Installation

To install the package, use the following command:

```sh
npm i @wanna/orange-money-api


Usage

Here’s an example of how to use the orange-money-api package:

const OrangeMoneyAPI = require('orange-money-api');

const authHeader = 'YOUR_AUTH_HEADER';
const marchantKey = 'YOUR_MARCHANT_KEY';
const returnUrl = 'YOUR_RETURN_URL';
const cancelUrl = 'YOUR_CANCEL_URL';
const notifUrl = 'YOUR_NOTIF_URL';

const orangeMoneyAPI = new OrangeMoneyAPI(authHeader, marchantKey, returnUrl, cancelUrl, notifUrl);

// Example payment details
const paymentDetails = {
  // Your payment details here
};

// Create a payment session
orangeMoneyAPI.createPaymentSession(paymentDetails)
  .then(response => {
    console.log('Payment session created:', response);
  })
  .catch(error => {
    console.error('Error creating payment session:', error);
  });

// Get transaction status
const orderId = 'ORDER_ID';
const amount = 'AMOUNT';
const payToken = 'PAY_TOKEN';

orangeMoneyAPI.getTransactionStatus(orderId, amount, payToken)
  .then(response => {
    console.log('Transaction status:', response);
  })
  .catch(error => {
    console.error('Error getting transaction status:', error);
  });


API
getAccessToken()
Fetches the access token. This is called automatically within other methods if the token is not already set.

createPaymentSession(paymentDetails)
Creates a payment session. Returns the response data.

Parameters:

paymentDetails (object): The payment details required by the Orange Money Web Payment API.
Example:
const paymentDetails = {
  // Your payment details here
};

orangeMoneyAPI.createPaymentSession(paymentDetails)
  .then(response => {
    console.log('Payment session created:', response);
  })
  .catch(error => {
    console.error('Error creating payment session:', error);
  });


getTransactionStatus(orderId, amount, payToken)
Gets the transaction status. Returns the response data.

Parameters:

orderId (string): The order ID.
amount (string): The amount of the transaction.
payToken (string): The payment token.
Example:

const orderId = 'ORDER_ID';
const amount = 'AMOUNT';
const payToken = 'PAY_TOKEN';

orangeMoneyAPI.getTransactionStatus(orderId, amount, payToken)
  .then(response => {
    console.log('Transaction status:', response);
  })
  .catch(error => {
    console.error('Error getting transaction status:', error);
  });


License
This project is licensed under the MIT License. See the LICENSE file for details.

Contributing
Contributions are welcome! Please open an issue or submit a pull request for any improvements or bug fixes.

Issues

If you encounter any issues, please open an issue on the GitHub repository.

Acknowledgements
Thanks to the developers and maintainers of the Orange Money Web Payment API.
