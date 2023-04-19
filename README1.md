# Telebirr Documentation

This class provides an interface for interacting with the Telebirr payment gateway API.
Initialization

The Telebirr class is initialized with the following parameters:

app_id (string): The app ID obtained from Telebirr.
app_key (string): The app key obtained from Telebirr.
public_key (string): The public key obtained from Telebirr.
notify_url (string): The URL to which Telebirr will send a notification when the payment is completed.
receive_name (string): The name of the person receiving the payment.
return_url (string): The URL to which the customer will be redirected after completing the payment.
short_code (string): The short code for the payment.
subject (string): The subject of the payment.
timeout_express (int): The time in minutes for the payment to expire.
total_amount (float): The total amount to be paid.
nonce (string): A unique identifier for the payment request.
out_trade_no (string): The transaction ID for the payment request.

Methods
request_params()

Returns a dictionary containing the request parameters.
send_request()

Sends a request to the Telebirr API and returns the response.
decrypt(public_key, payload)

Decrypts the payload using the given public key and returns the decrypted data as a dictionary.
Static Methods
encrypt(public_key, msg)

Encrypts the message using the given public key and returns the encrypted message as a string.
__encrypt_ussd(ussd, public_key)

```

from telebirr import Telebirr

telebirr = Telebirr(
    app_id='your_app_id',
    app_key='your_app_key',
    public_key='your_public_key',
    notify_url='https://your_notify_url.com',
    receive_name='your_receive_name',
    return_url='https://your_return_url.com',
    short_code='your_short_code',
    subject='your_subject',
    timeout_express=30,
    total_amount=100.0,
    nonce='your_nonce',
    out_trade_no='your_out_trade_no'
)

response = telebirr.send_request()

decrypted_response = telebirr.decrypt(public_key='your_public_key', payload=response['ussd'])

```

Encrypts the ussd dictionary using the given public key and returns the encrypted data as a string.
__sign(ussd, app_key)

Returns a string containing the signature for the given ussd dictionary and app key.
