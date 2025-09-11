O **DNF** (Dandified YUM) é o gerenciador de pacotes moderno em distribuições baseadas em **RPM** (Fedora, RHEL 8+, CentOS Stream, Rocky Linux). Ele substituiu o **YUM**, oferecendo melhor desempenho e resolução de **dependências**.

###### INSTALAR UM PACOTE:
``dnf install nome_pacote
###### REINSTALA UM PACOTE:
``dnf reinstall nome_pacote 

###### ATUALIZAR TODOS OS PACOTES:
``dnf update
###### ATUALIZAR UM PACOTE:
``dnf update nome_pacote

###### REMOVER PACOTE:
``dnf remove nome_pacote

###### PESQUISAR PACOTES:
``dnf search nome_pacote

###### VERIFICAR PACOTES INSTALADOS:
``dnf list installed

###### LISTAR PACOTES DISPONÍVEIS PARA INSTALAÇÃO:
``dnf list available

###### LISTAR PACOTES COM ATTs DISPONÍVEIS:
``dnf list updates

###### VERIFICAR INFORMAÇÕES SOBRE ALGUM PACOTE:
``dnf info nome_pacote

###### LIMPAR O CACHE DOS PACOTES:
``dnf clean all

### **4️⃣ Gerenciamento de Repositórios**

|                Comando                |           Descrição            | Exemplo                                                   |
| :-----------------------------------: | :----------------------------: | --------------------------------------------------------- |
|            ``dnf repolist             | Lista repositórios habilitados | `dnf repolist`                                            |
| `dnf config-manager --add-repo <URL>` |  Adiciona um novo repositório  | `sudo dnf config-manager --add-repo https://example.repo` |
