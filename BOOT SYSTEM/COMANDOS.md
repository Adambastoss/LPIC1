
##### **dmesg**: 
O comando '**dmesg**' exibe mensagens do kernel e do sistema geradas durante o **processo** de **inicialização**. Ele é útil para diagnosticar problemas relacionados ao **hardware** e ao **kernel**.
<<<<<<< HEAD
O comando `dmesg` não é específico de um sistema de inicialização, seja `sysvinit` ou `systemd`. Ele é um utilitário do Linux que exibe as mensagens do buffer circular do kernel. Esse buffer registra mensagens relacionadas ao hardware, inicialização do sistema, drivers e outros eventos do kernel. Tanto sistemas que usam `sysvinit` quanto `systemd` podem utilizar o comando `dmesg`.

- Verifica os eventos de inicialização nos arquivos de log.

**journalctl**:
O journalctl substituiu o **dmesg** no **systemd**
Permite uma versão mais completa dos logs, filtros mais específicos

Qual comando do journalctl exibe apenas mensagens de erro? 
**journalctl -p err**

Como você pode visualizar mensagens do journal relacionadas a um serviço específico, como **sshd**? **journalctl -u sshd**

Qual opção do journalctl permite visualizar mensagens do journal em tempo real?
**journalctl -f**

Como você pode limitar a saída do journalctl para mensagens registradas nos últimos 10 minutos?
**journalctl --since '10 minutes ago'**

Qual comando do journalctl exibe mensagens em ordem inversa, começando pelas mais recentes?
**journalctl -r**

Qual comando lista todos os meus boots?
**journalctl --list-boots**

**wall**
Serve para ==enviar mensagens para todos os usuários atualmente conectados ao sistema==.
**wall** "O sistema será reiniciado em 5 minutos. Por favor, salve seu trabalho."





[[BOOT]]