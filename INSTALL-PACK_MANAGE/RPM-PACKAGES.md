##### **RPM** (*baixo nível*)

1. Instale, reinstale, atualize e remova pacotes usando RPM, YUM e Zypper.
	**INSTALAR UM PACOTE:**
	``rpm -ivh nome_pacote.rpm``
	
	- `-i`: instala o pacote
	    
	- `-v`: modo verboso
	    
	- `-h`: mostra barra de progresso
	
	**ATUALIZAR UM PACOTE:**
	``rpm -Uvh nome_pacote.rpm``
	
	- `-U`: atualiza ou instala se o pacote não existir. Remove versão antiga e instala uma nova.
	
	**REMOVER UM PACOTE:**
	``rpm -e nome_pacote``



2. Obtenha informações sobre pacotes RPM, como versão, status, dependências, integridade e assinaturas.

	**LISTA OS PACOTES INSTALADOS:**
	``rpm -q [opções] nome_pacote
	Opções úteis:
	
	- `-qa`: lista todos os pacotes instalados
	    
	- `-qi`: mostra informações do pacote (incluindo **versão**)
		
	- `-qc`: lista arquivos de configuração do pacote
	    
	- `-qd`: lista arquivos de documentação do pacote
	
	**VERIFICA A INTEGRIDADE DO PACOTE:**
	- ``rpm -V``
	Verifica se arquivos foram modificados desde a instalação.
	
	**VERIFICAR DEPENDÊNCIAS:**
	- ``rpm -qpR nome-do-pacote.rpm ``        # para pacote não instalado
	- ``rpm -qR nome-do-pacote ``                 # para pacote instalado



3. Determine quais arquivos um pacote fornece, bem como descubra de qual pacote um arquivo específico vem.

	**LISTA TODOS OS ARQUIVOS INSTALADOS POR UM PACOTE:**
	- ``rpm -ql nome_pacote

	**ENCONTRAR QUAL PACOTE PERTENCE UM ARQUIVO:** 
	- ``rpm -qf caminho do arquivo


##### **rpm2cpio**

O `rpm2cpio` é uma ferramenta útil para **extrair** o conteúdo de um pacote RPM sem instalá-lo no sistema. Ele converte o pacote RPM no formato cpio (um formato de arquivamento), permitindo que você acesse os arquivos contidos no pacote.

## Para que serve?

1. **Extrair arquivos específicos de um pacote RPM** sem instalar o pacote completo
    
2. **Inspecionar o conteúdo** de um pacote antes da instalação
    
3. **Recuperar arquivos** quando você não quer/pode instalar o pacote completo
    
4. **Verificar conflitos** antes da instalação


 **SINTAXE BÁSICA:**
``rpm2cpio pacote.rpm | cpio -idmv
## Componentes do Comando Explicados

- `rpm2cpio`: Converte o pacote RPM para stream cpio
    
- `|`: Pipe (redireciona a saída para o próximo comando)
    
- `cpio`: Manipula arquivos no formato cpio
    
    - `-i`: Extrai arquivos
        
    - `-d`: Cria diretórios quando necessário
        
    - `-m`: Preserva timestamps (datas de modificação)
        
    - `-v`: Modo verboso (mostra o progresso)

##### LISTAR O CONTEÚDO DO ARQUIVO **SEM EXTRAIR**:

``rpm2cpio pacote.rpm | cpio -t

- `-t`: Lista conteúdo (quando não quer extrair)