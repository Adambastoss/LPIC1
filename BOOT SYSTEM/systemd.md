
**Principais diretórios:**

├──==/etc/systemd/system/==
│   ├── ✅ PRIORIDADE MAIS ALTA
│   ├── Armazena unidades personalizadas pelo administrador
│   ├── Substitui as unidades padrão
│   └── Local de overrides (ex: override.conf)

├── ==/lib/systemd/system/==   ou   ==/usr/lib/systemd/system/==
│   ├── 📦 INSTALADO PELOS PACOTES
│   ├── Contém unidades padrão do sistema
│   └── NÃO deve ser editado diretamente

├── ==/usr/lib/systemd/user/==
│   ├── 📦 Unidades de usuário instaladas por pacotes
│   └── Similar ao /lib/systemd/system/, mas no contexto do usuário

├── ==/run/systemd/system/==
│   ├── ⚡ TEMPORÁRIO (runtime)
│   ├── Unidades geradas em tempo de execução
│   └── Desaparecem após reboot

Principais características:

- Paraleliza a inicialização dos serviços, acelerando o boot.
    
- Usa _unit files_ (arquivos de unidade) para definir como serviços e recursos devem ser gerenciados.
    
- Oferece ferramentas para monitorar e controlar o estado do sistema.

## 🧩 **Principais tipos de unidades no `systemd`:**

| **Tipo de Unidade** | **Extensão** | **Descrição**                                                              |
| ------------------- | ------------ | -------------------------------------------------------------------------- |
| `service`           | `.service`   | Gerencia **serviços e daemons** (ex: `sshd.service`)                       |
| `socket`            | `.socket`    | Gerencia **sockets** usados para ativar serviços sob demanda               |
| `target`            | `.target`    | Agrupa unidades; equivale a "runlevels" no SysVinit                        |
| `device`            | `.device`    | Representa dispositivos do kernel detectados por udev                      |
| `mount`             | `.mount`     | Representa **pontos de montagem** (ex: `/home`)                            |
| `automount`         | `.automount` | Configura **montagem automática** de dispositivos                          |
| `swap`              | `.swap`      | Gerencia **espaços de swap**                                               |
| `timer`             | `.timer`     | Executa unidades baseadas em **tempo agendado** (substitui cron)           |
| `path`              | `.path`      | Monitora **arquivos ou diretórios** e aciona serviços quando há alterações |
| `slice`             | `.slice`     | Controla grupos de processos (cgroups) — **gerenciamento de recursos**     |
| `scope`             | `.scope`     | Criado automaticamente para processos externos ao systemd                  |

Principal comando para controlar estas unidades:
**systemctl**

# Ver o status de um serviço
systemctl **status** sshd

# Iniciar, parar e reiniciar um serviço
systemctl **start** nginx
systemctl **stop** nginx
systemctl **restart** nginx

# Ativar ou desativar serviços no boot
systemctl **enable** apache2
systemctl **disable** apache2

# Verificar se o serviço está habilitado no boot
systemctl **is-enabled** mysql

# Listar todas as unidades
systemctl l**ist-units** --type=service

# Recarregar arquivos de unidade após alteração
systemctl **daemon-reexec**
systemctl **daemon-reload**

# Ver o tempo de boot e análises
systemd-analyze

Exibir os serviços que mais **demoraram** para iniciar durante o boot:
systemd-analyze blame


Mudar **imediatamente** para outro target:
systemctl **isolate** multi-user.target

Definir um target padrão no boot:
systemctl **set-default** graphical.target

Verificar o target atual:
systemctl **get-default**








[[BOOT]]

