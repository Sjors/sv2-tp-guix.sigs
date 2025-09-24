Guix signature attestations for https://github.com/Sjors/sv2-tp releases.

For the general process see:
- https://github.com/bitcoin-core/guix.sigs
- https://github.com/Sjors/sv2-tp/tree/master/contrib/guix

Since there's currently no Windows release, it's necessary to enumerate all hosts:

```sh
HOSTS="arm64-apple-darwin x86_64-linux-gnu x86_64-apple-darwin arm-linux-gnueabihf aarch64-linux-gnu riscv64-linux-gnu powerpc64-linux-gnu" contrib/guix/guix-build
```

And then for codesigning:

```sh
HOSTS="arm64-apple-darwin x86_64-apple-darwin" contrib/guix/guix-codesign
```

The detached signatures are here: https://github.com/Sjors/sv2-tp-guix.sigs

Attestation doesn't require the `HOSTS` list, so it's the same as usual, e.g.:

```sh
env SIGNER=Sjors NO_SIGN=1 ./contrib/guix/guix-attest
```
