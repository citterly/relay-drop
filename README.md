# relay-drop

Encrypted file drops. Every file here is a tar.gz encrypted with GPG symmetric AES-256. Nothing in this repo is readable without the passphrase, which is never stored here.

## To open one on Windows (Git Bash, which ships gpg)

```
curl -LO https://raw.githubusercontent.com/citterly/relay-drop/main/<name>.tgz.gpg
gpg --decrypt --output <name>.tgz <name>.tgz.gpg
tar -xzf <name>.tgz
```

If `gpg` is missing but `openssl` is present, the drop will also be published as `<name>.tgz.enc` (openssl aes-256-cbc, pbkdf2) and opens with:

```
openssl enc -d -aes-256-cbc -pbkdf2 -in <name>.tgz.enc -out <name>.tgz
```

## Drops

- `drop-2026-10-07-test.tgz.gpg` — channel test: one HTML page and a README.
- `drop-2026-10-07-parse-pack.tgz.gpg` — GASW-028 parse pack: README, task files 27/28/29 with stage-1 rulings folded in, decisions file, parse design copy, stage-1 ERD page (7 files). `.enc` twin for openssl.
