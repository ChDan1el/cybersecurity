## [natas0](http://natas0.natas.labs.overthewire.org)
###### Usuário: natas0
###### Senha: natas0

Ao entrar no desafio nos deparamos com essa dica:

<img width="623" height="157" alt="image" src="https://github.com/user-attachments/assets/9d4d364c-21ac-4223-841c-0a47c4d0c82e" />

Então, usando o DevTools, ou seja, inspecionando o HTML da página, conseguimos a flag como um comentário HTML

<img width="1397" height="645" alt="image" src="https://github.com/user-attachments/assets/5578c4a6-aa82-45b8-aa40-539fe1899ffb" />

### **FLAG:** scfWG6qNEIdzqVyfRwEGXyNUfFZkZeQ7

## [natas1](http://natas1.natas.labs.overthewire.org)
###### Usuário: natas1
###### Senha: scfWG6qNEIdzqVyfRwEGXyNUfFZkZeQ7

Agora nesse desafio, não podemos inspecionar a página usando o botão direito do mouse

<img width="609" height="153" alt="image" src="https://github.com/user-attachments/assets/32f392ed-f508-4593-8bfc-62ed4eddec78" />

Então usaremos o atalho **Ctrl + U** para visualizar o código fonte da página. E lá já temos a flag

<img width="1070" height="331" alt="image" src="https://github.com/user-attachments/assets/858a1448-d982-4339-8deb-1e205c6899e9" />

### **FLAG:** vsDOxoXyq3wckCP1ZmTZ71ngIA606odB

## [natas2](http://natas2.natas.labs.overthewire.org)
###### Usuário: natas2
###### Senha: vsDOxoXyq3wckCP1ZmTZ71ngIA606odB

Analisando o código fonte da página, encontro a imagem "pixel.png" nela

<img width="1073" height="272" alt="image" src="https://github.com/user-attachments/assets/3e15e53c-0fdc-4c1d-ae40-f6cf15053f4f" />

Clicando no link da imagem, sou direcionado para a imagem, contendo somente a imagem de 1 pixel branco

<img width="76" height="76" alt="Captura de tela 2026-07-01 162744" src="https://github.com/user-attachments/assets/456b1c10-ae5a-46d3-be7d-e24a00b09c1c" />

Mas oque importa é a sua URL, pois nele mostra que essa imagem está armazenada no diretório "/files"

<img width="509" height="36" alt="image" src="https://github.com/user-attachments/assets/50aecd2a-dcca-4a0c-ab0a-67af44a02a6f" />

Então, acessando o diretório "/files", encontro dois arquivos: o primeiro sendo a imagem e o segundo sendo uma lista de usuários

<img width="352" height="33" alt="image" src="https://github.com/user-attachments/assets/9194516d-2efb-44e1-b2a7-d74cd6dae3b2" />

<img width="659" height="291" alt="image" src="https://github.com/user-attachments/assets/5923ad33-827b-4179-b480-9921dba3317d" />

Clicando para ver a lista de usuário, nele contém o nome e a senha de login dos usuários, dentre a senha do natas3 é a nossa flag

<img width="304" height="114" alt="image" src="https://github.com/user-attachments/assets/9fc6a198-0f11-4fe8-adc1-ba8868e40f8c" />

### **FLAG:** K30JrSRHzjxq3paUQuwozY4MNvmNFyhI

## [natas3](http://natas3.natas.labs.overthewire.org)
###### Usuário: natas3
###### Senha: K30JrSRHzjxq3paUQuwozY4MNvmNFyhI

Inspecionando a página recebo a seguinte dica:
<img width="1081" height="276" alt="image" src="https://github.com/user-attachments/assets/06fca5a1-0f68-4e3d-9ab2-5fc32195798d" />

Ela quer dizer que nem mesmo o google poderá achar, ou seja, a página que procuramos não está indexada. Nos levando a pasta [robots.txt](https://www.cloudflare.com/pt-br/learning/bots/what-is-robots-txt/)

<img width="650" height="126" alt="image" src="https://github.com/user-attachments/assets/71014ea0-67e1-4b26-800d-cc52e9051f4d" />

Nessa página se encontra um diretório não indexado chamado "/s3cr3t/".

Acessando esse caminho nos deparamos com outro diretório com arquivos, só que agora contento apenas o "users.txt"

<img width="645" height="323" alt="Captura de tela 2026-07-01 165038" src="https://github.com/user-attachments/assets/4a59ed77-411b-4f6d-9531-57d13c6251a8" />

Acessando esse arquivos conseguimos a flag

<img width="687" height="119" alt="image" src="https://github.com/user-attachments/assets/4c5e558a-e2a1-4b43-8af5-d1fb820de25a" />

### **FLAG:** JDrPnuZAKyl6MkiqQGFIddrqpvgOASth

## [natas4](http://natas4.natas.labs.overthewire.org)
###### Usuário: natas4
###### Senha: JDrPnuZAKyl6MkiqQGFIddrqpvgOASth

Ao entrar no desafio nos deparamos com essa exigência: "Os usuários só terão acesso à flag se vierem do natas5"

<img width="586" height="158" alt="image" src="https://github.com/user-attachments/assets/6a1dc169-3157-4113-8f2f-8ea392489b8a" />

Então para contornar esse problema, usaremos o **Burp Suite**.

Nós vamos interceptar a [requisição HTTP](https://www.hostinger.com/br/tutoriais/servidor-proxy) do desafio para alterar a origem da requisição, fazendo o
**Referer** mudar de "natas4" para "natas5"

Então vamos lá: Primeiro vamos abrir o **Burp Suite**, ir em **Proxy** e abrir o browser. Depois logamos no natas4

<img width="964" height="479" alt="image" src="https://github.com/user-attachments/assets/ab06ea80-d6d0-47e4-bb01-0e2a23f15d86" />

Agora vamos ligar o "Intercept Off" e recarregar a página para interceptar a requisição HTTP. Logo depois mudaremos o **Referer** de "**natas4.natas.labs.overthewire.org**" para "**natas5.natas.labs.overthewire.org**"

<img width="1026" height="724" alt="image" src="https://github.com/user-attachments/assets/c271635d-43c2-4feb-b995-0a074c5229bc" />

E para enviar a requisição para o servidor clicamos em "Foward", agora retornando ao desafio conseguiremos a flag

<img width="962" height="449" alt="image" src="https://github.com/user-attachments/assets/e4a4a2f0-4276-4814-a734-156021396ade" />

### **FLAG:** e4z2Noy3oqwPJUWzJH0dseN67Cn1sy2M

## [natas5](http://natas5.natas.labs.overthewire.org)
###### Usuário: natas5
###### Senha: e4z2Noy3oqwPJUWzJH0dseN67Cn1sy2M

Ao entrar no desafio temos essa mensagem: "Acesso negado. Você não está logado". Isso dá uma dica sobre os [cookies](https://www.kaspersky.com.br/resource-center/definitions/cookies) do site

<img width="475" height="105" alt="image" src="https://github.com/user-attachments/assets/ff5bd92b-47fb-4b49-ad5b-271e982ee533" />

Ao acessar os cookies temos que o "loggedin" está com valor 0, oque em liguagem binária significa negação.

<img width="945" height="179" alt="image" src="https://github.com/user-attachments/assets/4a71fbac-34b5-408a-a9e6-338e617efeb8" />

Então mudaremos o valor de "loggedin" de 0 para 1, onde o 1 significa positivo. Fazendo isso já ganhamos a flag

<img width="1027" height="473" alt="image" src="https://github.com/user-attachments/assets/5143ef0d-d0be-4115-8c84-2f92db53b8d7" />

### **FLAG:** 7mhjtShJAcld2NYbKHEadnhEwRn2P8VT

## [natas6](http://natas6.natas.labs.overthewire.org)
###### Usuário: natas6
###### Senha: 7mhjtShJAcld2NYbKHEadnhEwRn2P8VT

Ao entrar no desafio já é nos disponibilizado visualizar o código da página. Onde teremos que achar uma chave para receber a flag

<img width="556" height="145" alt="image" src="https://github.com/user-attachments/assets/01b9ef9c-b28c-40b8-af90-ec165a0889f3" />

Acessando "sourcecode" do desafio, temos um código php nele

<img width="519" height="191" alt="image" src="https://github.com/user-attachments/assets/6f2ad455-58b9-41ce-92d7-1a444e881758" />

Onde a função "include" chama um outro arquivo presente no servidor para o código da página.

Acessando o arquivo chamado, nós conseguimos a chave para o desafio

<img width="776" height="144" alt="image" src="https://github.com/user-attachments/assets/802ef4cc-5cf9-43cd-b17a-d917a7a19e14" />

Ao inserir a chave **FOEIUWGHFEEUHOFUOIU** no input, conseguimos a flag

<img width="584" height="203" alt="image" src="https://github.com/user-attachments/assets/4e300005-6684-4ec8-829a-7f13bc0b3f49" />

### **FLAG:** B1szg95UcTnrzwnF3i3TzYHlyYh8iBV0

## [natas7](http://natas7.natas.labs.overthewire.org)
###### Usuário: natas7
###### Senha: B1szg95UcTnrzwnF3i3TzYHlyYh8iBV0 

Ao acessar este desafio, são apresentados dois botões: Home e About.
Ao clicar em qualquer um deles, a aplicação faz uma requisição para `index.php` utilizando o parâmetro GET `page`, por exemplo:
> index.php?page=home

<img width="689" height="287" alt="image" src="https://github.com/user-attachments/assets/0a63f580-8840-4138-a8a9-e6f00ee67641" />

O parâmetro `page` é utilizado pela aplicação para definir qual arquivo será carregado e exibido ao usuário.
Como por exemplo, ao colocar `home` no parâmetro `page`, é retornado a página `Home`

Analisando o código fonte da página temos uma dica:

<img width="566" height="45" alt="image" src="https://github.com/user-attachments/assets/be3ee691-c733-4026-9657-3d764590bfb2" />

Então, utilizando a dica para poder resolver esse desafio, vamos colocar `/etc/natas_webpass/natas8` no parâmetro `page`, para poder acessar a flag

<img width="1000" height="300" alt="image" src="https://github.com/user-attachments/assets/dfb16d5e-d5d1-455b-96fc-9a69ae3ba7b9" />

### **FLAG:** ugXL95KQmUAJJj6bMezOlBNDyI9Imwkc 

## [natas8](http://natas8.natas.labs.overthewire.org)
###### Usuário: natas8
###### Senha: ugXL95KQmUAJJj6bMezOlBNDyI9Imwkc 

Depois de entrar no desafio, é pedido uma senha para poder exibir a flag

<img width="594" height="173" alt="image" src="https://github.com/user-attachments/assets/f21cb60a-fd0f-4a8a-a966-0b1c6fb4fee3" />

Clicando em `View sourcecode`, conseguimos ver como que verifica se a senha certa ou errada

<img width="487" height="318" alt="image" src="https://github.com/user-attachments/assets/124bb9ca-157d-4d42-b2d6-874b758f5f0e" />

Nele é comparado se ao codificar o input `'secret'` em `encodeSecret()` é igual à `$encodedSecret`.
Então é basicamente decodificar `$encodedSecret` para achar a senha

<img width="391" height="82" alt="image" src="https://github.com/user-attachments/assets/5d358cfd-44bd-4199-bfbf-650e823b11b9" />

O código funciona assim:
> base64_encode() , Primeiro pega o input e codifica em base64
> 
> strrev() , Depois inverte os caracteres da string
> 
> bin2hex() , E por fim codifica para hexadecimal

Entao devemos fazer o processo inverso com o `$encodedSecret`

```php
<?php
$encodedSecret = "3d3d516343746d4d6d6c315669563362";

$senha = base64_decode(strrev(hex2bin($encodedSecret)));

echo $senha;
?>
```

> hex2bin() , Decodifica de hexadecimal
>
>  strrev() , Inverte os caracteres da string
>
> base64_decode() , E por fim decodifica de base64

Assim temos a chave:
```
oubWYf2kBq 
```

Colocando a chave em `Input secret:` obtemos a flag

<img width="592" height="210" alt="image" src="https://github.com/user-attachments/assets/384a9596-421d-4b58-887d-93fd353a9480" />

### **FLAG:** UdxmI27dTaXmnd1rxKQTfws6jihTdcQ9

## [natas9](http://natas9.natas.labs.overthewire.org)
###### Usuário: natas9
###### Senha: UdxmI27dTaXmnd1rxKQTfws6jihTdcQ9

Depois de entrar no desafio temos um buscador de palavras, onde ao inserir algo nele, é retornado uma string contento os caracteres do input

<img width="520" height="326" alt="image" src="https://github.com/user-attachments/assets/0f944717-8c10-4f9f-b156-7c70ae9ed370" />

Então vamos analisar como isso funciona clicando em `View sourcecode`

<img width="335" height="163" alt="image" src="https://github.com/user-attachments/assets/c942006b-4668-4b29-9cf6-8513033c69e7" />

No código o input é diretamente inserido no comando de busca sem nenhuma sanitização, ou seja, abusaremos de um **OS Injection**

Vamos testar então se funciona mesmo, usaremos o seguinte input: `; ls`. O `;` serve para quebrar a linha de comando e executar `ls`

<img width="586" height="218" alt="image" src="https://github.com/user-attachments/assets/36746995-00f9-444e-ae7f-e142cb977735" />

Funcionou!! Retornou a lista de arquivos contido no diretório presente e não uma string contendo `ls`

Agora vamos usar uma dica dada na página inicial do CTF natas:

<img width="1651" height="74" alt="image" src="https://github.com/user-attachments/assets/281a6cf9-69e4-42d0-82f5-f8aa27b37341" />

Nele diz que toda senha da próxima fase está guardada em `/etc/natas_webpass/natas~`.
Nós queremos a senha do natas10, então vamos procurar em `/etc/natas_webpass/natas10`

Para isso usaremos o comando `cat` para poder ler oque há lá. Então o input ficará:
```
; cat /etc/natas_webpass/natas10
```

<img width="455" height="139" alt="image" src="https://github.com/user-attachments/assets/06cddf31-3b79-4d32-83d4-9ce83026965d" />

### **FLAG:** EgjlkzB6E8LJyf2Obt4q7q4ewt5ZWSNv

## [natas10](http://natas10.natas.labs.overthewire.org)
###### Usuário: natas10
###### Senha: EgjlkzB6E8LJyf2Obt4q7q4ewt5ZWSNv

Ao entrarmos no natas10, nos deparamos é basicamente o natas9, mas com filtro no *input*. 

<img width="551" height="289" alt="image" src="https://github.com/user-attachments/assets/adec4108-e7df-4843-907b-2fbe70884ad9" />

Então vamos ver como o código funciona

<img width="394" height="208" alt="image" src="https://github.com/user-attachments/assets/82315bd9-c63f-4d33-a0d6-3a36ecc4a191" />

O filtro bloqueia apenas os caracteres /[;|&]/, mas o $ não está entre eles. Isso significa que ainda é possível injetar comandos usando o operador $

<img width="497" height="363" alt="image" src="https://github.com/user-attachments/assets/91d85a23-ab0c-4041-a0ce-72d9991973de" />

Com isso funcionando, utilizo o operador $ para acessar o arquivo da flag e lê-lo diretamente:

```
$ cat /etc/natas_webpass/natas11
```
<img width="485" height="256" alt="image" src="https://github.com/user-attachments/assets/16a19f5f-3fb3-4cc2-a66f-061117d26785" />

### **FLAG:** VUMQDmuITOEHzhviLE5V0VG9cPMQkyxd
