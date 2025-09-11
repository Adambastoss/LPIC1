#### `sed
Permite **editar texto em fluxo** , ou seja, modificar arquivos **linha a linha** sem abrir um editor interativo.

`sed 's/Uva/Abacate/' frutas.txt 
**Substitui** a palavra **Uva** pela palavra Abacate  

`sed '/^$/d' frutas.txt
**Deleta** as linhas vazias do começo ao final do arquivo.

`sed -i 's/Uva/Abacate/g' frutas.txt
**Substitui** diretamente no arquivo (em definitivo)

------------------------------------------------------------------------

#### `sha256sum

Os comandos **`sha256sum`e`sha512sum no Linux funcionam de forma semelhante ao md5sum

Eles são usados principalmente para **verificar a integridade e proteção** dos arquivos, garantindo que não foram prejudicados ou alterados.

## Diferença entre SHA-256 e SHA-512

| Algoritmo   | Tamanho do hash                        | Segurança                                       | Velocidade                                     |
| ----------- | -------------------------------------- | ----------------------------------------------- | ---------------------------------------------- |
| **SHA-256** | 256 bits → 64 caracteres hexadecimais  | Muito seguro, padrão atual em várias aplicações | Mais rápido que SHA-512 em sistemas de 32 bits |
| **SHA-512** | 512 bits → 128 caracteres hexadecimais | Ainda mais seguro (mais difícil quebrar)        | Mais rápido em sistemas de 64 bits             |

------------------------------------------------------------------------

#### ``sort

Serve para **Ordenar** linhas de texto em um arquivo ou da entrada padrão (stdin).

`sort frutas.txt
Ordena as frutas em ordem alfabética.

`sort -n numeros.txt
Ordena em ordem númerica

`sort -r numeros.txt
Ordena em ordem reversa

`sort -t ":" -k2 departments.txt
**-t** **":"**= Define dois pontos como separador
**-k2** = Diz que a consulta será ordenada pela segunda coluna

![[Pasted image 20250823225032.png]]

------------------------------------------------------------------------

#### `tr
Você quase sempre usará ele com um pipe (`|`) ou redirecionamento.
#### `echo "hello world" | tr 'a-z' 'A-Z'
==Saída==:  **HELLO WORD**
Converte as letras maiúsculas em minúsculas.

#### `echo "Muito     espaço" | tr -s ' '
==Saída==: **Muito espaço** 
Compacta mútiplos espaços em um espaço simples

#### `echo "My phone is 61994336210" | tr -d '0-9'
==Saída==: **My phone is**
Remove todos os números

#### `echo "My phone is 123456" | tr -cd '0-9'
==Saída==: **123456**
Inverte a lógica. **Remove** tudo que **não seja** número.
**-c '0-9'** significa tudo que não seja dígito de 0 a 9 
**-d** Apaga tudo que não é dígito

| Flag        | Significado           | Exemplo de Uso               | Por que é Cobrada                                       |
| ----------- | --------------------- | ---------------------------- | ------------------------------------------------------- |
| (Nenhuma)   | Substituição simples  | `tr 'a' 'b'`                 | Funcionalidade central do comando.                      |
| `-s`        | Compactar repetições  | `tr -s ' '`                  | **Muito comum para limpar espaços e quebras de linha.** |
| `-d`        | Deletar caracteres    | `tr -d '0-9'`                | Habilidade essencial para filtragem.                    |
| `-c`        | Usar complemento      | `tr -cd '0-9'`               | Conhecimento avançado para soluções elegantes.          |
| `[:class:]` | Classes de caracteres | `tr '[:lower:]' '[:upper:]'` | Uso de padrões POSIX para portabilidade.                |

---------------------------------------------------------------


#### `uniq
O comando `uniq` é usado para **identificar ou filtrar linhas repetidas consecutivas** em um arquivo ou fluxo de texto.


#### `uniq arquivo.txt
uniq sem flag, remove todas as linhas repetidas consecutivas.

![[Pasted image 20250826204816.png]]

#### `uniq -c cores.txt
**-c** precede todas as linhas com o número de vez que ela se repetiu consecutivamente.

![[Pasted image 20250826205617.png]]

#### `uniq -u cores.txt
-u (unique) Mostra apenas linhas que não se repetiram.

#### `uniq -d cores.txt
Mostra apenas as linhas que se repetiram

------------------------------------------------------------------------

#### `wc

#### `wc -l cores.txt
Conta **linhas**

#### `wc -c cores.txt
Conta **caracteres**

#### `wc -w cores.txt
Conta **palavras**

------------------------------------------------------------------------

#### `xzcat
Tanto `zcat` quanto `xzcat` são utilitários para **visualizar o conteúdo de arquivos compactados sem precisar descompactá-los explicitamente**.


