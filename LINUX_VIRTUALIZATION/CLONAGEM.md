
Entenda as propriedades exclusivas de um sistema Linux que precisam ser **alteradas** quando um sistema é **clonado** ou usado como modelo

## 1. Identificadores de Máquina Únicos

### **Hostname**

- O nome da máquina deve ser único na rede
    
- Localização:
    
    - `/etc/hostname`
        
    - Também presente em `/etc/hosts` (geralmente associado a 127.0.1.1)
        

### **UUIDs de Partições**

- Identificadores únicos para sistemas de arquivos
    
- Verifique com `blkid` ou `lsblk -f`
    
- Pode ser regenerado para partições não-root:
    
    bash
    
    ``tune2fs -U random /dev/sdXN


## 2. Configurações de Rede

### **Endereço MAC**

- Cada interface de rede deve ter um MAC único
    
- Gerenciado por:
    
    - `/etc/udev/rules.d/70-persistent-net.rules` (em sistemas mais antigos)
        
    - `nmcli` ou arquivos de configuração em `/etc/NetworkManager/`
        

### **Endereços IP**

- Configurados em:
    
    - `/etc/network/interfaces` (Debian/Ubuntu)
        
    - `/etc/sysconfig/network-scripts/` (RHEL/CentOS)
        
    - Configurações do NetworkManager


## 3. Chaves e Identificadores de Segurança

### **SSH Host Keys**

- Localizados em `/etc/ssh/ssh_host_*_key*`
    
- Gerar novos:
    
    bash
    
    ``rm /etc/ssh/ssh_host_*
    ``dpkg-reconfigure openssh-server  # Debian/Ubuntu
    ``ssh-keygen -A  # Distribuições em geral
    

### **Machine ID**

- Identificador único do sistema em `/etc/machine-id`
    
- Para regenerar:
    
    bash
    
    ``rm /etc/machine-id systemd-machine-id-setup
    

### **DBUS Machine ID**

- `/var/lib/dbus/machine-id`
    
- Pode ser regenerado removendo o arquivo (será recriado no boot)

## 4. Logs e Arquivos Temporários

- Limpar logs antigos:
     
    ``rm -rf /var/log/*
    
- Limpar arquivos temporários:
    
    ``rm -rf /tmp/*
    

## 5. Configurações Específicas de Aplicações

### **Crontabs**

- Verificar `/var/spool/cron/` para tarefas agendadas de usuários
    
- Verificar `/etc/crontab` e `/etc/cron.d/`
    

### **Sistema de Arquivos Temporários**

- `/etc/fstab` pode conter UUIDs específicos que precisam ser atualizados