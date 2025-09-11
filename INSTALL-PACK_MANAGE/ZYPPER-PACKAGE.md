O **Zypper** é o gerenciador de pacotes padrão em distribuições **openSUSE** e **SUSE Linux Enterprise (SLE)**. Ele é uma ferramenta poderosa para instalar, atualizar e gerenciar pacotes **RPM** nesses sistemas. Para a certificação **LPIC-1**, é essencial conhecer seus principais comandos.

###### INSTALAR:
``zypper install pacote

###### REMOVER:
``zypper remove pacote

###### ATUALIZA TODOS OS PACOTES:
``zypper update
###### APLICA APENAS ATTs DE SEGURANÇA:
``zypper patch
###### LISTA PACOTES COM ATTs DISPONÍVEIS:
``zypper list-updates

###### BUSCA PACOTES POR TERMO:
``zypper search termo
###### LISTA PACOTES INSTALADOS:
``zypper packages --installed-only

###### EXIBE INFORMAÇÕES DE UM PACOTE:
``zypper info pacote

###### LISTA REPOSITÓRIOS HABILITADOS:
``zypper repos  

###### ADICIONA UM REPOSITÓRIO:
``zypper addrepo

###### ATUALIZAR METADADOS DOS REPOS:
``zypper refresh

###### VERIFICA DEPENDÊNCIAS QUEBRADAS:
``zypper verify

###### ENCONTRA QUAL PACOTE FORNECE UM ARQUIVO:
``zypper what-provides arquivo

### **6️⃣ Histórico de Transações**

| **Comando**        | **Descrição**                        | **Exemplo**           |
| ------------------ | ------------------------------------ | --------------------- |
| `zypper history`   | Mostra todas as operações realizadas | `sudo zypper history` |
| `zypper undo <ID>` | Reverte uma transação específica     | `sudo zypper undo 5`  |
