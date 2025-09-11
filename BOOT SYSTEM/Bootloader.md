**GRUB** **2**

Gerenciador de boot

Comando para instalação:
**grub-install**

Comando para atualizar o grub:
**update-grub**
Geralmente será utilizado após alguma edição do grub em ==/etc/default/grub==
Caso não haja o comando update-grub, utilizar o comando **grub-mkconfig**

Arquivo para inserir **entradas personalizadas** no menu de inicialização:
/etc/grub.d/==40_custom==


### ⚙️ `grub.cfg`

- **Pertence ao GRUB 2 (a versão moderna e padrão atual)**
    
- **Função:** É o principal arquivo de configuração de boot, gerado automaticamente pelo `update-grub`
    
- **Local comum:** `/boot/grub/grub.cfg`
    
- **Importante:** NÃO deve ser editado manualmente. As configurações vêm de arquivos como `/etc/default/grub` e scripts em `/etc/grub.d/` 

- Adicione ou modifique scripts em `/etc/grub.d/` para **personalizações avançadas**


### 🧾 `menu.lst`

- **Pertence ao GRUB Legacy (versões anteriores ao GRUB 2)**
    
- **Função:** Define os sistemas operacionais disponíveis para boot e suas opções (kernel, initrd, etc.)
    
- **Local comum:** `/boot/grub/menu.lst`
Para acessar o grub legacy (antigo) - pressiona tecla **c** na iniciação do grub 2

### 🗃️ `grub.conf`

- **Esse é praticamente um link simbólico para o** `menu.lst` nas distribuições que usam GRUB Legacy
    
- **Local:** Usualmente aparece como `/boot/grub/grub.conf`, mas na prática é só uma forma alternativa de referenciar o `menu.lst`
    
- **Função:** Mesmo papel — mostrar opções de boot para o GRUB Legacy



Arquivo que armazena os parâmetros de configuração do **Kernel**:
/boot/==config-5.7.0==
Esse arquivo é gerado automaticamente quando um kernel é instalado ou compilado, e não deve ser modificado diretamente pelo usuário.


É uma tabela de consulta que armazena nomes de símbolos.
/boot/==System.map==


**initramfs**

**(Initial RAM Filesystem)** é um **sistema de arquivos temporário** carregado na **memória RAM durante o processo de boot** do Linux.

## 🔧 Para que serve?

O `initramfs` resolve um problema: o **kernel precisa acessar o disco** para montar o `/`, mas pode **não ter suporte embutido para certos drivers de disco, controladores, LVM, RAID ou sistemas de arquivos criptografados**.

📌 Então, o `initramfs` entra em ação para:

1. Carregar **módulos do kernel** (como drivers de disco, LVM, RAID, etc.).
    
2. Descobrir e montar o **sistema de arquivos raiz**.
    
3. Passar o controle da inicialização para o **init** do sistema real (como o `systemd`).

## 🛠️ Como funciona?

1. O **bootloader** (ex: GRUB) carrega dois arquivos:
    
    - O **kernel** (`vmlinuz-...`)
        
    - O **initramfs** (`initrd.img` ou `initramfs-...img`)
        
2. O kernel descompacta o `initramfs` na RAM e monta como sistema de arquivos raiz temporário.
    
3. Scripts dentro do `initramfs` localizam a partição raiz real (`/`) e montam.
    
4. O controle é passado para o sistema real (como `/sbin/init` ou `systemd`).


Diferença entre `initrd` e `initramfs`
O **initrd** tem a basicamente a mesma função do **initramfs**, porém é mais antigo. O `initrd` é mais comum em sistemas legados, enquanto o `initramfs` é o padrão atual.

| Característica  | `initrd`                            | `initramfs`                      |
| --------------- | ----------------------------------- | -------------------------------- |
| Tipo de arquivo | Imagem de disco (geralmente ext2)   | Arquivo compactado (cpio + gzip) |
| Montagem        | Montado como um **loopback device** | Extraído diretamente na memória  |
| Persistência    | Precisa ser desmontado              | Descartado automaticamente       |
| Flexibilidade   | Menos flexível                      | Mais leve e moderno              |
| Kernel support  | Suportado por kernels mais antigos  | Padrão em kernels modernos       |






[[BOOT]]

