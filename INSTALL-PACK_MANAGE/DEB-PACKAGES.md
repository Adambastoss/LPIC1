
 **Principais áreas de conhecimento:**

- Instalar, atualizar e desinstalar pacotes binários do Debian.
- Encontre pacotes contendo arquivos ou bibliotecas específicas que podem ou não estar instalados.
- Obtenha informações do pacote, como versão, conteúdo, dependências, integridade do pacote e status da instalação (se o pacote está instalado ou não).
- Consciência de apt.

- **/etc/apt/sources.list**
		Ele contém uma lista de repositórios onde o APT busca pacotes para instalação, atualização e remoção.

- dpkg
- dpkg-reconfigure
- apt-get
- apt-cache

##### **Extensão padrão** de pacotes Debin é **.deb**
Temos gerenciadores de pacotes de **baixo** nível e de **alto** nível

==Baixo== nível: **Não** tratam dependências
Gerenciador de baixo nível padrão: **dpkg**


==INSTALAR UM PACOTE:==
**dpkg -i pacote.deb**

==LISTA TODOS OS ARQUIVOS DE UM PACOTE INSTALADO:==
**dpkg -L nome_pacote**

==REMOVER UM PACOTE:==
**dpkg -r nome_pacote**

==REMOVER TODOS OS ARQUIVOS E RESQUÍCIOS DE UM PACOTE REMOVIDO:==
**dpkg --purge** **nome_pacote**
**dpkg -P** **nome_pacote**

==MOSTRAR AS INFORMAÇÕES DE UM PACOTE:==
**dpkg --info pacote.deb**

==LISTAR TODOS OS PACOTES INSTALADOS:==
**dpkg -l**

==RECONFIGURAR UM PACOTE INSTALADO:==
**dpkg-reconfigure nome_pacote**

==CONFIGURAR UM PACOTE:==
**dpkg --configure nome_pacote**

==BUSCAR PACOTES QUE POSSUEM DETERMINADO ARQUIVO==
**dpkg -S nome_arquivo**
### 🧠 Contexto:

Durante a instalação de um pacote `.deb`, o `dpkg` segue basicamente **duas etapas**:

1. **Extração dos arquivos** do pacote no sistema.
    
2. **Execução dos scripts de configuração**, como `postinst`, `preinst`, etc.
    

Se algo falhar **durante a configuração**, o pacote ficará com o status de **"unconfigured"**. É aí que o `dpkg --configure` entra.








# **GERENCIADOR DE PACOTES** de ==ALTO NÍVEL==

Resolve todas as dependências de forma automática

- `apt`:
    
    É o comando recomendado para o uso diário, oferecendo uma interface mais simples e intuitiva. 
    
- `apt-get`:
    
    Continua funcional e compatível, mas pode ser considerado uma opção mais de baixo nível, especialmente útil em casos específicos ou scripts mais antigos.

**ATUALIZA A LISTA DE PACOTES DISPONÍVEIS:**
==apt-get update==

**ATUALIZA TODOS OS PACOTES INSTALADOS:** (Sem alterar dependências)
==apt-get upgrade==

**ATUALIZA TODOS OS PACOTES INSTALADOS E TAMBÉM LIDA COM MUDANÇAS DE DEPEND.**
==apt-get dist-upgrade==

**INSTALA UM PACOTE:**
==apt-get install nome_pacote==

**REMOVE UM PACOTE (MANTÉM ARQUIVOS DE CONFIGURAÇÃO):**
==apt-get remove nome_pacote==

**REMOVE UM PACOTE E SEUS ARQUIVOS DE CONFIGURAÇÃO:**
==apt-get purge nome_pacote==

**REMOVE PACOTES INSTALADOS COMO DEPENDENCIA E NÃO MAIS NECESSÁRIOS:**
==apt-get autoremove==

**CORRIGIR DEPENDÊNCIAS QUEBRADAS:**
==apt-get install -f==

### COMANDOS COM ==apt-cache==

**PROCURA PACOTES RELACIONADOS A UM TERMO:**
==apt-cache search termo==

**MOSTRA AS DEPENDÊNCIAS DE UM PACOTE:**
==apt-cache depends nome_pacote==

**MOSTRA DETALHES DO PACOTE:**
==apt-cache show nome_pacote==

**LISTA TODOS OS PACOTES QUE ESTÃO DISPONÍVEIS PARA INSTALAÇÃO:**
==apt-cache pkgnames==


## 🧠 Principais comandos `apt` para a LPIC-1

| ==Comando==                      | Função                                                                          |
| ---------------------------- | ------------------------------------------------------------------------------- |
| ==`apt update`==                 | Atualiza a lista de pacotes disponíveis nos repositórios                        |
| ==`apt upgrade`==                | Atualiza todos os pacotes instalados para as versões mais recentes              |
| ==`apt install nome_do_pacote`== | Instala um novo pacote                                                          |
| ==`apt remove nome_do_pacote`==  | Remove um pacote (mantém arquivos de configuração)                              |
| ==`apt purge nome_do_pacote`==   | Remove completamente o pacote, incluindo arquivos de configuração               |
| ==`apt autoremove`==             | Remove pacotes que não são mais necessários                                     |
| ==`apt search termo`==           | Pesquisa por pacotes nos repositórios                                           |
| ==`apt show nome_do_pacote`==    | Mostra detalhes sobre um pacote                                                 |
| ==`apt list`==                   | Lista pacotes disponíveis, instalados ou atualizáveis                           |
| ==`apt full-upgrade`==           | Similar ao `dist-upgrade`: atualiza pacotes e lida com mudanças de dependências |
| ==`apt clean`==                  | Limpa o cache de pacotes baixados                                               |
