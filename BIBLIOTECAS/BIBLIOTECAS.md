Temos bibliotecas **estáticas** e bibliotecas **compartilhadas** (dInâmicas)

Bibliotecas **estáticas**: O código da biblioteca é incorporado ao código do programa. O programa passa a não ter dependência de libs em tempo de execução (externas), mas em compensação ficam mais pesados.

Sempre terminam com a letra **a**
Ex: ==libpthread.a==


Bibliotecas **compartilhadas**: Apenas uma cópia da biblioteca precisa ser disponibilizada em tempo de execução, e pode ser utilizadas por diversos programas ao mesmo tempo. O código do programa precisa ter apenas um link que aponte para essa lib externa. O Código fica mais leve.

soname:
	- **nome** da biblioteca (normalmente prefixo **lib**)
	- **so** (shared object - objeto compartilhado)
	- **versão** da biblioteca



**PRINCIPAIS DIRETÓRIOS:**

## 🔍 Localizando bibliotecas compartilhadas

As bibliotecas costumam estar nos diretórios:

- `/lib`
    
- `/lib64`
    
- `/usr/lib`
    
- `/usr/lib64`

- /usr/local/lib/
    
- Outros locais configurados via variável ou arquivo de configuração.


### 📁 Diretórios principais:

| Diretório    | Uso comum                                                               |
| ------------ | ----------------------------------------------------------------------- |
| `/lib`       | Bibliotecas essenciais para o sistema (arquitetura 32 bits ou genérica) |
| `/lib64`     | Bibliotecas para sistemas 64 bits                                       |
| `/usr/lib`   | Bibliotecas de programas não essenciais do sistema                      |
| `/usr/lib64` | Versão 64 bits das bibliotecas em `/usr/lib`                            |
### 📌 Explicação rápida:

- **`/lib`e`/lib64`** : usado para bibliotecas que o sistema precisa **logo na inicialização** .  
    Ex: bibliotecas usadas pelo `/bin/sh`ou `/sbin/init`.
    
- **`/usr/lib`e`/usr/lib64`** : armazenam bibliotecas de programas que **não são críticas para o boot** , mas são usadas no dia a dia.


### `/etc/ld.so.conf` e `/etc/ld.so.conf.d/`

Esses arquivos informam ao sistema onde procurar bibliotecas adicionais.

- `/etc/ld.so.conf`: arquivo principal; 
		Esse arquivo contém apenas uma linha: ==include /etc/ld.so.conf.d/*.conf==
		que aponta para os arquivos que estão dentro do diretório `/etc/ld.so.conf.d/*.conf`)
		

- `/etc/ld.so.conf.d/*.conf`: arquivos adicionais incluídos automaticamente.


**COMANDOS IMPORTANTES:**

### `ldconfig`

Gerenciar ou cache de bibliotecas compartilhadas no sistema. Ele:

- Atualiza (**cria**) o conjunto de links simbólicos das bibliotecas;
    
- Cria (atualiza) o **cache** `/etc/ld.so.cache`;
- **Criação do cache**: Após processar todos os arquivos, o comando `ldconfig` é executado (normalmente durante a instalação de pacotes) para criar ou atualizar o arquivo de cache `/etc/ld.so.cache`. Este arquivo de cache é uma lista otimizada e binária de todas as bibliotecas encontradas.
- **Tempo de execução**: Quando um programa precisa de uma biblioteca, o carregador dinâmico consulta o cache `/etc/ld.so.cache` para encontrar o caminho correto de forma rápida, em vez de procurar nos diretórios um a um.
    
- Leia os diretórios padrão e os listados em `/etc/ld.so.conf`.

- **Deve ser executado sempre que se adiciona um arquivo de configuração** ou realiza alguma modificação dentro do diretório  ==/etc/ld.so.conf.d/==


### `ldd`
Serve para **listar as bibliotecas compartilhadas** (dynamic libraries) que um determinado **programa** ou biblioteca **precisa** para funcionar, porém você precisa especificar o **caminho completo** do binário, conforme o exemplo abaixo:

Ex: **ldd** ==/usr/bin/ls==
Comando exibe todas as libs que o comando ls precisa para funcionar.

### `objdump`
Exibe **informações detalhadas** sobre arquivos **objeto**, como executáveis e bibliotecas.

### Variável de ambiente `LD_LIBRARY_PATH`

Define diretórios adicionais de bibliotecas **apenas durante a execução**.

bash

CopyEdit

`LD_LIBRARY_PATH=/meu/caminho/lib ./meu_programa`