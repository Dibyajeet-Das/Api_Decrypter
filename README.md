# Api_Decrypter
## 🔓 What Does This Do?

This command sends an **encrypted API payload** to `decrypter.php`, which is a PHP script responsible for **decoding and decrypting sensitive data** so developers can analyze or debug it.

```bash
curl --location 'http://localhost/insight_proxy_api_v1_0/decrypter.php' \
--header 'Content-Type: text/plain' \
--data 'U2FsdGVkX19E3s2aaZWYZB5NlpuezfoPPDCmgtVpoVOu7PYeYzYYuMoBnpi6dRTLpBzG8y/MHeo5S7uwo4F5HaEdFxDD5OvXLBjFcYF072NSWka6wh8zeee4+df1yjiC4K7HgELTQZPdvC4NC5A/Nfbg6vAyD+ZlqbCXJQ8DfSNi5l7225MF0iJ2+13GPmstCaVYpQbSWG+Ng9JtvbczWguG9R97UG1gfqkMU/sSaoY='
How It Works:
The payload (U2FsdGVkX19E3s2a…) is Base64-encoded, AES-encrypted data.

The prefix U2FsdGVkX1 decodes to Salted__, which is how OpenSSL formats AES-encrypted data.

This ensures the data is secure during transmission.

decrypter.php:

Accepts the encrypted text.

Decodes it from Base64.

Decrypts it using a shared key/password and salt.

Outputs the original, human-readable data (such as API responses, configs, or tokens).

Useful for:

Debugging encrypted API payloads.

Inspecting tokens or configurations in a secure local environment.

Testing API responses without exposing secrets in plaintext.
