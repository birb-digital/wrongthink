# wrongthink

wrongthink chat v2:
* is peer-to-peer
* has end-to-end encryption (Double Ratchet over DTLS (WebRTC))
* supports Markdown
* has notifications using MaterializeCSS
* is verifiable

### IMPORTANT: no warranty is provided with this software. you are using it at your own risk. please see [SECURITY.md](SECURITY.md) for more info
### ALSO IMPORTANT: wrongthink.me must use certain data in order for the service to run properly. please see [SECURITY.md](SECURITY.md) for more info

## use
* [bleeding edge](https://birb.digital/wrongthink)
* [stable](https://wrongthink.me)

## credits
wrongthink.me would not be possible without the following libraries:
* [TweetNaCl.js (cryptography)](https://github.com/dchest/tweetnacl-js) and [its](https://github.com/dchest/tweetnacl-util-js) [addons](https://github.com/dchest/tweetnacl-auth-js)
* [double-ratchet (cryptography, made in house!)](https://github.com/birb-digital/double-ratchet)
* [DOMPurify (security)](https://github.com/cure53/DOMPurify)
* [MaterializeCSS (UI)](https://github.com/materializecss/materialize)
* [JQuery (UI)](https://github.com/jquery/jquery)
* [markdown-it (UI)](https://github.com/markdown-it/markdown-it)
* [js-emoji (UI)](https://github.com/iamcal/js-emoji)
* [twemoji (UI)](https://github.com/twitter/twemoji)

## how are things derived
### fingerprint
the fingerprint used for connection is derived from the SHA-512 hash of the public key. the fingerprint is converted into 8 words (with a word list of 256 words), allowing for 2^64 combinations. this makes it somewhat suitable for identity verification but **it is not recommended unless security is not a concern**.
### safety number
the safety number is derived from `SHA512(xPublic + yPublic)`, where both keys are the identity keys of the peers. the hash is converted to 16 words (with a word list of 256 words), allowing for 128 bits of security. the order of the fingerprints is determined by the first byte of the public identity keys.
### file uploading
file uploading uses an extension to the double ratchet library we use. the steps are as follows:
- take `encrypt(Base64(our random 32-byte file key))`
- set the resulting object's `hasFile` property to true
- set the resulting object's `file` property to a new object containing:
  - the property `encrypted`: `Base64(raw_encrypt(file, our random 32-byte file key, nonce))`
  - the property `nonce`: `Base64(our random 32-byte nonce)`

## custom clients
custom clients are as easy as 1, 2, 3. just use PeerJS and use https://wrongthink.me:8080 as the PeerJS server. from there, you'll need to use [parabirb/double-ratchet](https://github.com/parabirb/double-ratchet) to handshake and send messages.

## running it
just open `index.html` in the browser of your choice.

## terminology
* arachat is the name of the wrongthink client
* wrongthink2 is the messaging protocol
* wrongthink is the name of the service

## misc
`v2.0.html` is the old version of wrongthink2 which used OTRv3. it is now obsolete (NOT compatible with any new clients) and kept only for educational purposes. `v1.html` is the old version of wrongthink which was not E2EE. it is still usable with server `wss://wrongthink.me:9764` but not recommended. it is also kept only for educational purposes.

## legal
```
>implying i give a shit about export regulations
```

no warranty is provided with this software. please read [SECURITY.md](SECURITY.md) for more information. please read our [code of conduct](CODE_OF_CONDUCT.md) before contributing.
