# Ferramentas online:

## Para quebrar HASH

### [Hashes.com](https://hashes.com/en/decrypt/hash)  (Mais eficiente e versátil)

### [CrackStation](https://crackstation.net/)

## Ferramentas para identificar tipo de HASH

### [Hashes.com](https://hashes.com/en/tools/hash_identifier)

### [hash-id.py](https://gitlab.com/kalilinux/packages/hash-identifier/-/tree/kali/master)

# Ferramentas do kali linux para quebrar HASH:

## John the Ripper:

<img width="225" height="225" alt="image" src="https://github.com/user-attachments/assets/71dcfbe0-798d-4191-8c2a-cd885452f37f" />

Formatação do comando `john`

> john --format=[TIPO_DE_HASH] --wordlist=[PATH_DA_WORDLIST] [ARQUIVO_COM_O_HASH]

Exemplo:

```
john --format=raw-md5 --wordlist=/usr/share/wordlists/rockyou.txt hash.txt
```

O `raw` em `--format` é usado com tipos de hash populares, como MD5, SHA1, SHA256, SHA512 e NTLM. 

