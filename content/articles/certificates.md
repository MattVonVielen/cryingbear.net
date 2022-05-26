---
title: "Public-Key Infrastructure (or, Why You Should Learn to Stop Worrying and Grudgingly Accept Certificates)"
date: 2022-05-11T16:05:31-06:00
draft: true
---

MISCONCEPTION: THE RELATIONSHIP BETWEEN CERTIFICATES AND CRYPTOGRAPHY

Though they are used in the process of encrypting or signing things, the encryption function of Certificates is far less important to security than their primary function, which is that of Identity and Trust. In fact, one of the most significant applications for their cryptography aspect is in the support and implementation of the Identity function.

<!-- Define cryptography, then asymmetric -->
ALL THE CRYPTO YOU NEED TO KNOW TO CONTINUE:

There is a technique called “asymmetric encryption”, which uses pairs of encryption keys, one Public and one Private. (This is also called Public Key Encryption.)  They are usually used one at a time; the Public Key is used to encrypt data, and the Private Key is used to decrypt that same data. Encrypted data using one Public Key cannot be decrypted by anyone who doesn’t have the corresponding Private Key, including the original sender/encrypting entity. In addition to encryption, these keys are also used for “signing” data, providing a way to prove whether the data has been changed since it was signed; a Private Key is used to make the signature, and the corresponding Public Key is used to verify it.

It’s not at all necessary to understand how this technique works, just that it exists and has the properties described above.

Public keys are just that - public information. Sharing public keys is not only safe to do, but also necessary for others to be able to encrypt things that you (and only you) can decrypt. Certificates only contain Public Key information, and as such are not typically considered sensitive information. Private keys, on the other hand, should be handled with as much sensitivity as a password, if not more.

SO, WHAT EVEN IS A CERTIFICATE THEN?

A Certificate is a Public Key plus some metadata describing the key. The metadata always includes a validity period (start and end dates outside of which the key shouldn’t be used) as well as a canonical name (CNAME for short) of the owning entity. Modern Certificates also contain a lot of other metadata, notably key usages which list the intended allowed usages for the key; a certificate can have any number of usages including things like “server authentication” (for server-side TLS), “client authentication” (for TLS mutual-authentication), “code signing”, “email protection”, “digital signature”, “key signing” and many more. (Custom, non-standard key usages can even be specified for extremely specialized applications.)

Certificates fill the role of tying someone or something’s identity to its Public Key in a way that can be verified to some level of trust. This allows you to receive another entity’s Public Key and encrypt data to send to them with the confidence that they are the entity they claim to be, and not an unknown party trying to snoop on your traffic.

WHERE WOULD I USE CERTIFICATES?

These days, mostly on web (or other kinds of) servers using the TLS (Transport Layer Security) protocol standard. However, in order to explain the security workflow that certificates enable I’ll first briefly look at a different usage that’s a bit less common but still important: the S/MIME protocols for email encryption and digital signatures.

WHO USES S/MIME?

The US Department of Defense uses S/MIME extensively. Many official business email exchanges with DoD personnel are required to be at least cryptographically signed, with more sensitive kinds of information requiring both signing and encryption of the message and any attachments.  As a result, it’s common for contractors working with the DoD to be issued special email certificates or even Smart Card security tokens (like CACs) which combine the certificates with some additional hardware security features.

Additionally, some commercial enterprises also use S/MIME for sensitive communication. Due to the sizable overhead of creating and maintaining a fully compliant PKI in current and historic market conditions, these tend to be quite large organizations (e.g., large multinational companies) which can afford a dedicated support team for this purpose.

COOL, HOW DOES IT WORK THEN?

A full detail of the S/MIME specification is far outside the scope of this document, but the brass tacks of signing an email are as follows:
•	Once the email body and/or attachments are complete (i.e., when the sending user clicks “send”), the sending user’s Private Key is used to generate a signature hash for the message
•	The message, attachment(s), the user’s signing certificate and the calculated signature are assembled into one or more envelope data structures which are added to the complete outgoing message.
•	The receiving user’s email application uses the included certificate to find the Public Key to use to validate the signature hash against the message and/or attachment(s).
•	If the signature fails to validate, the application indicates to the user that the message may have been tampered with somehow in its UX.
•	If the signature validates successfully, the certificate is then verified to ensure it comes from a trusted source; if it doesn’t, the application indicates this lack of trust to the user somehow in the UX.

Encrypted messages are similar (they are also signed), with the following additions:
•	The sending user must have access to the receiving user’s certificate before sending. (The recipient’s public key is needed to do the encrypting, as mentioned above.) This can be via an explicit sharing of the certificate (“Hey, could you please email me your certificate?”) or more often via a Directory Service lookup (Active Directory or other LDAP, for example).
•	The message/attachment(s) are encrypted before being included in the outgoing email.
•	After handling the signature as above, the recipient’s application uses their private key to decrypt any encrypted message parts for display, taking care to store the message locally in its encrypted form (if at all).

ALRIGHT, WHAT DOES THIS HAVE TO DO WITH TLS?

Admittedly not a whole lot, but there is conceptual overlap.

The idea behind TLS is we want to encrypt the traffic between our client and server. Rather than pick and choose which bits of our traffic are sensitive and only encrypt those, it’s far simpler to just use an entirely unencrypted protocol (e.g., HTTP) and create an abstraction layer around the network traffic that behaves the same to your application as if it wasn’t doing anything special. All the crypto lives in this abstraction layer, so your application just needs to focus on its business logic. That’s where TLS comes in; your application uses a TLS-capable client instead of a regular plaintext network client, but after the client is created and initialized, all the application really needs to know is how to call “Send()” with some plaintext. 


