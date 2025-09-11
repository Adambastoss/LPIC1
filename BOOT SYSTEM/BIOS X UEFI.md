A UEFI (Unified Extensible Firmware Interface) é uma evolução da BIOS, suportando discos **maiores que 2 TB** (Não tem limitação de discos), tabelas de partição **GPT** e oferecendo uma interface **gráfica** e recursos mais modernos. A BIOS, por outro lado, é mais limitada e utiliza tabelas de partição MBR.

A partição EFI (ESP - EFI System Partition) em sistemas UEFI geralmente utiliza o sistema de arquivos **FAT32**, pois ele é amplamente suportado e compatível com a maioria dos firmwares UEFI.

No Linux, o comando **ls /sys/firmware/efi** verifica se esse diretório existe. Se existir, o sistema foi inicializado no modo UEFI.

Uma das vantagens do UEFI em relação à BIOS é o suporte à inicialização segura (**Secure Boot**), que ajuda a proteger o sistema contra malware durante o processo de boot.

A UEFI requer o uso da tabela de partição **GPT** (GUID Partition Table) para inicializar sistemas, pois ela suporta discos maiores que 2 TB e oferece maior flexibilidade em comparação ao MBR.

[[BOOT]]