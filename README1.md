
<h1>Telebirr Class</h1>
<p>This class provides functionality for interacting with the Telebirr API.</p>
<h2>Constructor</h2>
<p>The constructor takes in the following parameters:</p>
<ul>
	<li><code>app_id</code>: The ID of the app.</li>
	<li><code>app_key</code>: The app key used to sign the request.</li>
	<li><code>public_key</code>: The public key used to encrypt the request.</li>
	<li><code>notify_url</code>: The URL to which the notification should be sent.</li>
	<li><code>receive_name</code>: The name of the receiver of the payment.</li>
	<li><code>return_url</code>: The URL to which the user should be redirected after the payment is completed.</li>
	<li><code>short_code</code>: The short code for the payment.</li>
	<li><code>subject</code>: The subject of the payment.</li>
	<li><code>timeout_express</code>: The timeout for the payment.</li>
	<li><code>total_amount</code>: The total amount of the payment.</li>
	<li><code>nonce</code>: A random nonce value.</li>
	<li><code>out_trade_no</code>: The trade number for the payment.</li>
</ul>

<h2>Methods</h2>

<h3>__encrypt_ussd</h3>
<p>A static method used to encrypt the request.</p>
<ul>
	<li><code>ussd</code>: The request body.</li>
	<li><code>public_key</code>: The public key used for encryption.</li>
</ul>

<h3>encrypt</h3>
<p>A static method used to encrypt the request using RSA.</p>
<ul>
	<li><code>public_key</code>: The public key used for encryption.</li>
	<li><code>msg</code>: The message to be encrypted.</li>
</ul>

<h3>__sign</h3>
<p>A static method used to sign the request.</p>
<ul>
	<li><code>ussd</code>: The request body.</li>
	<li><code>app_key</code>: The app key used for signing.</li>
</ul>

<h3>request_params</h3>
<p>A method that returns the request parameters.</p>

<h3>send_request</h3>
<p>A method that sends the request to the API and returns the response.</p>

<h3>decrypt</h3>
<p>A static method used to decrypt the response.</p>
<ul>
	<li><code>public_key</code>: The public key used for decryption.</li>
	<li><code>payload</code>: The payload to be decrypted.</li>
</ul>

```python
from telebirr import Telebirr

app_id = 'YOUR_APP_ID'
app_key = 'YOUR_APP_KEY'
public_key = 'YOUR_PUBLIC_KEY'
notify_url = 'https://example.com/notify'
return_url = 'https://example.com/return'
short_code = 'YOUR_SHORT_CODE'
subject = 'YOUR_SUBJECT'
timeout_express = '30m'
total_amount = 100
nonce = 'YOUR_NONCE'
out_trade_no = 'YOUR_OUT_TRADE_NO'

telebirr = Telebirr(
    app_id=app_id,
    app_key=app_key,
    public_key=public_key,
    notify_url=notify_url,
    receive_name='Test User',
    return_url=return_url,
    short_code=short_code,
    subject=subject,
    timeout_express=timeout_express,
    total_amount=total_amount,
    nonce=nonce,
    out_trade_no=out_trade_no
)

response = telebirr.send_request()
print(response)
```
