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

> john --wordlist=[path to wordlist] [path to file]

Exemplo:

```
john --format=raw-md5 --wordlist=/usr/share/wordlists/rockyou.txt hash.txt
```

O `raw` em `--format` é usado com tipos de hash populares, como MD5, SHA1, SHA256, SHA512 e NTLM. 

## Como quebrar hash variando o nome do usuario para a senha

Nós usaremos uma função do john, o `--single`. Ele varia o nome do usuario com outros caracteres para tentar acertar a senha, 

como: Joker, joker, JOKER, J0ker, jok3r, etc.

Para realizar esse comando, o arquivo com o hash deverá estar assim:

> nome:hash

E o comando será assim:

> john --single --format=[format] [path to file]

Exemplo:

Arquivo: mike:1efee03cdcb96d90ad48ccc7b8666033

```
john --single --format=raw-sha256 hashes.txt
```

## Quebrando senhas de arquivos .zip

Para isso, usamos o `zip2john`, segue o comando:

> zip2john [options] [zip file] > [output file]

Usar os 'options' não é necessário, exemplo:

```
zip2john secure.zip > zip_hash.txt
```

Logo depois, quebre o hash gerado pelo gerado pelo `zip2john`, como:

```
john --wordlist=/usr/share/wordlists/rockyou.txt zip_hash.txt
```



