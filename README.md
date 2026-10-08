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
- `drop-2026-10-07-parse-pack.tgz.gpg` — GASW-028 parse pack. Extract INSIDE the work `project-context/gasw-review/.memory/` folder: files land in place (`relay/2026-10-07-parse/PACK.md` is the note; `specs/GASW-028/...` is the payload). `.enc` twin for openssl.
- `drop-2026-10-08-unit28.tgz.gpg` — GASW-028 parse chain: resume at unit 28 (prompts only; 27 is done at work). Extract INSIDE the work `project-context/gasw-review/.memory/` folder → `relay/2026-10-08-unit28/`. `.enc` twin for openssl.
