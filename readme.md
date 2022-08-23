# DiSE

This repository contains the reference implementation of [DiSE: Distributed Symmetric-key Encryption](https://eprint.iacr.org/2018/727). This is only a proof of concept implementation and should not be considered production grade. Use at your own risk. 

Threshold cryptography provides a mechanism for protecting secret keys by sharing them among multiple parties, who then jointly perform cryptographic operations. An attacker who corrupts upto a threshold number of parties cannot recover the secrets or violate security. Prior works in this space have mostly focused on definitions and constructions for public-key cryptography and digital signatures, and thus do not capture the security concerns and efficiency challenges of symmetric-key based applications which commonly use long-term (unprotected) master keys to protect data at rest, authenticate clients on enterprise networks, and secure data and payments on IoT devices.

We propose a generic construction of threshold authenticated encryption based on any distributed pseudorandom function (DPRF). When instantiated with the two different DPRF constructions proposed by Naor, Pinkas and Reingold (Eurocrypt 1999) and our enhanced versions, we obtain several efficient constructions meeting different security definitions. We implement these variants and provide extensive performance comparisons. Our most efficient instantiation uses only symmetric-key primitives and achieves a throughput of upto 1 million encryptions/decryptions per seconds, or alternatively a sub-millisecond latency with upto 18 participating parties.


## Build Instructions

Linux
```
cmake --preset linux
cmake --build out/build/linux
```

Mac
```
cmake --preset osx
cmake --build out/build/osx
```

Windows
```
cmake --preset x64-Release
cmake --build out/build/x64-Release
```

Run the unit tests `out/build/<platform>/dEncFrontent /dEncFrontent -u`.
