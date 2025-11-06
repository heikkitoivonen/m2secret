## m2secret: AES encryption/decryption module in Python

m2secret is a simple encryption and decryption module and CLI utility built with the M2Crypto library (version 0.18 or later) to make it easy to secure strings and files from prying eyes. The serialized form does not follow any standards.

By default it will use 256-bit AES (Rijndael) symmetric-key cryptography in CBC mode. Key material is derived from submitted password using the PBKDF2 algorithm.

# Documentation

Sample usage:

    import m2secret

    # Encrypt
    secret = m2secret.Secret()
    secret.encrypt('my data', 'my master password')
    serialized = secret.serialize()

    # Decrypt
    secret = m2secret.Secret()
    secret.deserialize(serialized)
    data = secret.decrypt('my master password')

    assert data == 'my data'

## License

m2secret is Open Source software, licensed under the Apache License, 2.0.
