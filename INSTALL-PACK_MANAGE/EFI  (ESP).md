
**Partição especial em sistemas que usam firmware UEFI (Unified Extensible Firmware Interface)** — o sucessor do BIOS tradicional.

Ela **contém os arquivos necessários para iniciar o sistema operacional**, como:

- Bootloaders (ex: `grubx64.efi`, `systemd-bootx64.efi`)
    
- Drivers UEFI
    
- Arquivos de configuração (como `grub.cfg` ou arquivos do systemd-boot)
    
- Aplicativos UEFI (ex: diagnósticos ou atualizadores de firmware)


## 🧠 Características Técnicas da ESP

| Característica      | Detalhe                                             |
| ------------------- | --------------------------------------------------- |
| Tipo de sistema     | Usada em sistemas UEFI                              |
| Sistema de arquivos | ==FAT32== (exigido pelo padrão UEFI)                |
| Tamanho sugerido    | 100–500 MB (depende da distro e número de sistemas) |
| Ponto de montagem   | Geralmente montada em `/boot/efi` no Linux          |
| Tipo da partição    | Identificada pelo GUID: `EF00` (em GPT)             |

## 🧪 Exemplo prático de uso (ambiente real)

### 🔧 Cenário: Dual boot Linux + Windows

Você está configurando um computador com **Windows 11 e Ubuntu 22.04**. Ambos usam UEFI.

### Estrutura de partições (GPT):

|Partição|Tamanho|Tipo|Montagem|
|---|---|---|---|
|/dev/sda1|300 MB|EFI System (ESP)|/boot/efi|
|/dev/sda2|100 GB|NTFS (Windows)|(Windows C:)|
|/dev/sda3|50 GB|EXT4 (Linux)|/|

📁 Exemplo de estrutura de diretórios da ESP:

/boot/efi/
└── EFI/
    ├── BOOT/
    │   └── BOOTX64.EFI         # Bootloader padrão UEFI
    └── ubuntu/
        ├── grubx64.efi         # GRUB para Ubuntu
        └── shimx64.efi         # Secure Boot

### Explicação:

- Durante a instalação, o Windows criou a **ESP em /dev/sda1** e colocou seu próprio bootloader (`bootmgfw.efi`) lá.
    
- Ao instalar o Ubuntu, o instalador detectou a ESP e **adicionou o GRUB** (em `EFI/ubuntu/`) na mesma partição.
    
- O firmware UEFI lista as entradas de boot (via NVRAM) e permite escolher qual iniciar.



[[INSTALL-PACK_MANAG]]


