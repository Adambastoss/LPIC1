c## Objetivo principal do LVM:

> Permitir que você **crie, redimensione, combine, migre e gerencie volumes de armazenamento** de forma dinâmica — sem precisar reinicializar o sistema ou reinstalar o SO.

## 🧠 Conceitos-chave do LVM

| Conceito                 | Descrição                                                                                                            |
| ------------------------ | -------------------------------------------------------------------------------------------------------------------- |
| **PV (Physical Volume)** | Dispositivo físico ou partição usada pelo LVM (`/dev/sdb1`, `/dev/nvme0n1p1`)                                        |
| **VG (Volume Group)**    | Agrupamento de PVs, formando um “pool” de armazenamento                                                              |
| **LV (Logical Volume)**  | "Partições virtuais" criadas dentro de um VG, que o sistema enxerga como discos normais (`/dev/vg_data/lv_docs`)<br> |
| **PE (Physical Extent)** | Unidades de alocação dentro dos PVs (tamanho padrão: 4 MB)                                                           |
## 📁 Exemplo prático (ambiente real)

### 🎯 Cenário: Servidor de arquivos

Imagine que você gerencia um **servidor de arquivos corporativo** e recebe dois novos discos de 2 TB cada (`/dev/sdb` e `/dev/sdc`). Sua meta é criar um espaço unificado de 4 TB para armazenar documentos.

🔧 Etapas usando LVM:

# 1. Criar volumes físicos
sudo ==pvcreate== /dev/sdb /dev/sdc

# 2. Criar um volume group chamado "vg_docs"
sudo ==vgcreate== vg_docs /dev/sdb /dev/sdc

# 3. Criar um volume lógico de 3.5 TB chamado "lv_arquivos"
sudo ==lvcreate== -L 3.5T -n lv_arquivos vg_docs

# 4. Formatar o volume lógico
sudo mkfs.ext4 /dev/vg_docs/lv_arquivos

# 5. Montar o volume
sudo mkdir /mnt/arquivos
sudo mount /dev/vg_docs/lv_arquivos /mnt/arquivos


## 🔄 Vantagens do LVM

| Vantagem                       | Explicação                                                             |
| ------------------------------ | ---------------------------------------------------------------------- |
| **Redimensionamento dinâmico** | É possível aumentar/diminuir LVs em tempo real (com ou sem desmontar). |
| **Snapshots**                  | Permite criar cópias temporárias de um volume para backup.             |
| **Migração de dados**          | Mover dados entre discos sem downtime.                                 |
| **Agrupamento de discos**      | Combinar vários discos em um único volume lógico.                      |
