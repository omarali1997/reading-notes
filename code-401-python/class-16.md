# Read 16 : Cryptography

># Introduction to Cryptography

### Cryptography, or the art and science of encrypting sensitive information, was once exclusive to the realms of government, academia, and the military. However, with recent technological advancements, cryptography has begun to permeate all facets of everyday life.


### Everything from your smartphone to your banking relies heavily on cryptography to keep your information safe and your livelihood secure.

### And unfortunately, due to the inherent complexities of cryptography, many people assume that this is a topic better left to black hat hackers, multi-billion dollar conglomerates, and the NSA.But nothing could be further from the truth.



## cryptography includes both high level recipes and low level interfaces to common cryptographic algorithms such as symmetric ciphers, message digests, and key derivation functions. For example, to encrypt something with cryptography’s high level symmetric encryption recipe:

```python
from cryptography.fernet import Fernet
# Put this somewhere safe!
key = Fernet.generate_key()
f = Fernet(key)
token = f.encrypt(b"A really secret message. Not for prying eyes.")
token
b'...'
f.decrypt(token)
b'A really secret message. Not for prying eyes.'
```

# Installation
```
pip install cryptography
```

# Layout

### cryptography is broadly divided into two levels. One with safe cryptographic recipes that require little to no configuration choices. These are safe and easy to use and don’t require developers to make many decisions.

### The other level is low-level cryptographic primitives. These are often dangerous and can be used incorrectly. They require making decisions and having an in-depth knowledge of the cryptographic concepts at work. Because of the potential danger in working at this level, this is referred to as the “hazardous materials” or “hazmat” layer. These live in the cryptography.hazmat package, and their documentation will always contain an admonition at the top.




