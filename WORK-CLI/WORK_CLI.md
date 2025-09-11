
**pwd** -  Mostra o diretório local

**echo** ==“Qualquer coisa”== - Ecoar “Qualquer coisa” na tela

**uname -r** - Mostra a versão do Kernel

- **>** - ==Redirecionar== uma saída para algum lugar. Ex: Redicionar “nada a ver” para um arquivo chamado teste
		**echo** ==nada a ver== **>** ==teste==

Mesmo que o arquivo teste não exista, ele será criado com o texto “nada a ver”


- **>>**  - Append | **Acrescenta** um conteúdo dentro de um arquivo. Ex: Acrescentar “nada a ver” dentro do arquivo teste já existente:

	**echo** ==nada a ver== **>>** ==teste==

Caso o arquivo não exista, será criado. Mas como o arquivo teste já existia, o conteúdo do arquivo ficará assim agora: 
					**cat** ==teste==
					**nada a ver
					nada a ver

-----------------------------------------------------------------------
O pipe (`|`) **redireciona a saída de um comando para a entrada de outro**, enquanto `grep` **filtra linhas de texto** que correspondem a um padrão.

**| grep** - Pipe grep | ==Concatenar== comandos. 
	Ex: **uname -a** **| grep** ==LInux==

Este comando mostrará todos os arquivos que contém ==Linux== no nome

**set** - Visualizar ==variáveis Locais==.
**env** - Visualizar ==variáveis Globais==
**

**unset** - ==Remover== uma variável. 
	EX: unset $NOME_VARIAVEL

------------------------------------------------------------------------

**history** - LIsta todo o histórico de comandos
		Ex:   ==269 uname -a==
		    ==270 clear==

**history** **10** - Caso eu queira apenas os 10 últimos comandos
**!270** - ==Executa== o comando **clear** novamente
**history -d** **num-command** - ==Remove== um comando do histórico 
**history -c** - ==Limpa== o histórico da sessão ==atual== 

**history -w** - Salva a alteração, ==exclusão== de um comando ou do histórico completo, fazendo que o histórico não seja restaurado na próxima sessão.

------------------------------------------------------------------------
### **WHICH**
Localiza o **caminho** completo de um comando **executável** no sistema.
	Ex: `which mkdir
		Saída: **/usr/bin/mkdir**

------------------------------------------------------------------------
### **TYPE**

**==MOSTRA O CAMINHO ABSOLUTO DO EXECUTÁVEL==**
`type -p comando

**==MOSTRA APENAS O TIPO DO COMANDO==** (alias, builtin, file, function)
`type -t comando

**==MOSTRA TODAS AS OCORRÊNCIAS DO COMANDO NO PATH==**, incluindo **aliases**
`type -a comando

------------------------------------------------------------------------
##### Quoting

"Quoting" é o ato de usar **aspas** ou outros caracteres especiais para **controlar como o shell interpreta** certos símbolos, variáveis e caracteres.  
Isso é importante para evitar interpretações indesejadas e para trabalhar com strings contendo espaços, curingas (_wildcards_) ou caracteres especiais (`$`, `*`, `?`, `!`, `\`, etc.).

![[Pasted image 20250809142052.png]]
![[Pasted image 20250809142414.png]]
