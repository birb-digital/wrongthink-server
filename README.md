# wrongthink

wrongthink chat v2:
* is peer-to-peer
* has end-to-end encryption (Double Ratchet over PeerJS)
* supports Markdown
* has notifications using MaterializeCSS
* is verifiable

## credits
wrongthink.me would not be possible without the following libraries:
* [TweetNaCl.js (cryptography)](https://github.com/dchest/tweetnacl-js) and [its](https://github.com/dchest/tweetnacl-util-js) [addons](https://github.com/dchest/tweetnacl-auth-js)
* [double-ratchet (cryptography, made in house!)](https://github.com/birb-digital/double-ratchet)
* [MaterializeCSS (UI)](https://github.com/materializecss/materialize)
* [JQuery (UI)](https://github.com/jquery/jquery)
* [markdown-it (UI)](https://github.com/markdown-it/markdown-it)
* [js-emoji (UI)](https://github.com/iamcal/js-emoji)
* [twemoji (UI)](https://github.com/twitter/twemoji)

## security
![threat model](https://raw.githubusercontent.com/parabirb/wrongthink/master/threat%20model.png)

### this codebase is not audited and you are using this messenger at your own risk.

we do accept vulnerability reports (parabirb@protonmail.ch / @parabirb Twitter / parabirb#9968 Discord) and will patch them ASAP, but i cannot guarantee that wrongthink.me is secure.

## how are things derived
### fingerprint
the fingerprint used for connection is derived from the SHA-512 hash of the public key. the fingerprint is converted into 8 words (with a word list of 256 words), allowing for 2^64 combinations. this makes it somewhat suitable for identity verification but **it is not recommended unless security is not a concern**.
### safety number
the safety number is derived from `SHA512(xPublic + yPublic)`, where both keys are the identity keys of the peers. the hash is converted to 16 words (with a word list of 256 words), allowing for 128 bits of security. the order of the fingerprints is determined by the first byte of the public identity keys.

## custom clients
custom clients are as easy as 1, 2, 3. just use PeerJS and use https://wrongthink.me:8080 as the PeerJS server. from there, you'll need to use [parabirb/double-ratchet](https://github.com/parabirb/double-ratchet) to handshake and send messages.

## running it
just open `index.html` in the browser of your choice.

## misc
`v2.0.html` is the old version of wrongthink2 which used OTRv3. it is now obsolete (NOT compatible with any new clients) and kept only for educational purposes. `v1.html` is the old version of wrongthink which was not E2EE. it is still usable with server `wss://wrongthink.me:9764` but not recommended. it is also kept only for educational purposes.

## legal
```
>implying i give a shit about export regulations
```

no warranty is provided with this software and you waive all liability blah blah blah do whatever you want with this software idgaf

## WOKE!!!
no political pandering will ever take place on the site or in the repo. wrongthink will always be wrongthink and nothing more. i might put some memes on the page from time to time though.

[wrongthink.me will never accept cryptocurrency donations](https://www.schneier.com/blog/archives/2021/04/wtf-signal-adds-cryptocurrency-support.html)
