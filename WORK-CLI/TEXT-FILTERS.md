#### `seq  1 100 > numeros.txt

Cria o arquivo numeros.txt já preenchido com uma **sequência** de 1 a 100.

------------------------------------------------------------------------
#### `bzip2 -k compact.txt

**Compacta** o arquivo compact.txt no formato ==bz2==. O **-k** é de (keep), para ao converter, ==manter== na pasta o arquivo que foi compactado.
Arquivo compactado: **compact.txt.bz2**

#### `bzcat compact.txt.bz2
Consigo ver o conteúdo do arquivo que está compactado.

#### `bzcat compact.txt.bz2 | wc -w
## **Detalhes**

- **`wc`** significa **word count** (contagem de palavras).
    
- A opção **`-w`** faz com que ele conte apenas ==palavras==.

`wc` pode contar **linhas** (`-l`), **palavras** (`-w`) e **caracteres** (`-m` ou `-c` dependendo da versão).

#### `bzcat compact.txt.bz2 > recebendo.txt

Vai **jogar o conteúdo** do arquivo compact **para dentro** do arquivo recebendo.txt 

------------------------------------------------------------------------
#### `cat
 **Exibe** conteúdo de arquivos: `cat arquivo.txt

`cat arquivo1.txt arquivo2.txt > arquivo_combinado.txt
**Concatena** o conteúdo dos dois arquivos **direcionando** para um novo arquivo

`cat -n recebendo.txt
Exibe o conteúdo do arquivo em linhas numeradas
Ex: 
**1** Conteúdo arquivo1
**2** Conteúdo arquivo2

`cat -b recebendo.txt
A flag **-b** irá numerar apenas as linhas ==não vazias==.

`cat -E numeros.txt
Imprime com **caracteres de fim de linha** visíveis

Saída: 
		1,2,3==$==
		4,5,6==$==
		7,8,9==$==

------------------------------------------------------------------------
#### `cut
"**Cortar**" o documento e trazer apenas aquilo que você quer. É importante você analizar um documento antes de utilizar o comando, para verificar qual delimitador os dados estão utilizando e encontrar o melhor possível.

`cut -d "," -f 2 numeros.txt

**-d** = ==delimitador== será uma vírgula **' , '**
**-f** =  Pegue o segundo **2** ==field== (campo) de cada linha do arquivo **numero.txt**

Saída:
		2
		5
		8

`cut -d ',' -f 2,3 numeros.txt
Pego o ==field== 2 e 3

------------------------------------------------------------------------
#### `head numeros.txt
Pega as **10 primeiras** linhas do documento, por **padrão**.

`head -n 5 numeros.txt
**-n** = De ==numeric== **5**  de linhas = Pegar as 5 primeiras linhas de um documento.

------------------------------------------------------------------------
#### `less
**Visualiza arquivos** de forma **==interativa==** (paginado). 
Navegação: `Espaço` (próxima página), `b` (voltar), `/texto` (busca), `q` (sair).

-----------------------------------------------------------------------------------------------
#### `md5sum
No **Linux**, o comando **`md5sum`** serve para **calcular e/ou verificar o hash MD5** de um arquivo ou entrada de dados.

- **MD5** (_Message Digest 5_) é um algoritmo que gera um **resumo criptográfico** (hash) de **128 bits** representado como **32 caracteres hexadecimais**.
    
- É usado para **verificar integridade** de arquivos — ou seja, confirmar que não houve alteração nos dados.
    
- Não é seguro para uso criptográfico (colisões conhecidas), mas ainda é comum em verificações de integridade.

**Comando:**  `md5sum arquivo.txt
**Saída** típica: `d41d8cd98f00b204e9800998ecf8427e  arquivo.txt`

--------------------------------------------------------------------------
#### ``nl
Numera linhas
Ex: 
	``nl numeros.txt
Saída:
	 1  1,2,3
     2  4,5,6
     3  7,8,9

--------------------------------------------------------------------------

#### ``od

O comando **`od`** (_octal dump_) no Linux serve para **exibir o conteúdo de arquivos em formatos numéricos ou legíveis**,

``od -x numeros.txt
``-x`` Exibe em hexadecimal como no exemplo abaixo
**Saída**:
	0000000 2c31 2c32 0a33 2c34 2c35 0a36 2c37 2c38
	0000020 0a39
	0000022

``od -c numeros.txt
``-c`` Mostra caracteres legíveis e caracteres de controle em formato `\n`, `\t` etc.
**Saída:**
	0000000   1   ,   2   ,   3  \n   4   ,   5   ,   6  \n   7   ,   8   ,
	0000020   9  \n
	0000022

---------------------------------------------------------------------------
#### ``paste

O comando **`paste`** no Linux serve para **juntar linhas de arquivos lado a lado**, criando colunas separadas por um delimitador (por padrão, **TAB**).

``paste frutas.txt numeros.txt
**Saída:**
	banana  1,2,3
	pera       4,5,6
	maça      7,8,9

--------------------------------------------------------------------------

#### ``sed

