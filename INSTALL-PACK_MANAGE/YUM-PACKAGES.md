##### **YUM** (*alto nível*)
## **📌 Principais Características do YUM**

✅ **Resolução automática de dependências**  
✅ **Suporte a múltiplos repositórios** (configurados em `/etc/yum.repos.d/`)  
✅ **Histórico de transações** (permite desfazer operações)  
✅ **Assinatura GPG de pacotes** (verificação de integridade)  
✅ **Cache de metadados** (acelera buscas)

###### ARQUIVO DE CONFIGURAÇÃO PRINCIPAL:
***/etc/yum.conf***


###### **INSTALAR UM PACOTE:**
``yum install nome_pacote

###### **ATUALIZAR UM PACOTE ESPECÍFICO:**
``yum update nome_pacote

###### **ATUALIZAR TODOS OS PACOTES DE FATO** (*não os respositórios*)
``yum update

###### **REMOVER UM PACOTE:**
``yum remove nome_pacote

###### **PROCURAR PACOTES NOS REPOSITÓRIOS:**
``yum search

###### **MOSTRAR DETALHES DE UM PACOTE:**
``yum info nome_pacote

###### **LISTAR PACOTES INSTALADOS:**
``yum list installed

###### **LISTAR PACOTES DISPONÍVEIS PARA INSTALAÇÃO:**
``yum list available

###### **LISTA TODOS OS PACOTES COM ATUALIZAÇÕES DISPONÍVEIS:**

| Lista **detalhes** como versão atual e nova versão disponível.
	``yum list updates 	
	``yum check-update

## **Quando usar cada um:**

- Use **`yum check-update`** em scripts (para verificar via código de saída)
    
- Use **`yum list updates`** para consulta manual (mais legível para humanos)

###### **MOSTRAR AS DEPENDÊNCIAS DE UM PACOTE:**
``yum deplist nome_pacote

###### **DESCOBRE QUAL PACOTE FORNECE UM ARQUIVO:**
``yum provides <arquivo>

