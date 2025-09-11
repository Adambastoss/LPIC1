
- **Sistema de arquivos virtual** (como `/proc/`) que expõe informações sobre **dispositivos de hardware**, **drivers** e **configurações do kernel**.

- Organizado hierarquicamente por **dispositivos**, **barramentos** (PCI, USB) e **classes** (rede, blocos, input).

| **Diretório**   | **Descrição**                                                |
| --------------- | ------------------------------------------------------------ |
| `/sys/block/`   | Discos e dispositivos de bloco (ex: `sda`, `nvme0n1`).       |
| `/sys/bus/`     | Dispositivos organizados por barramento (PCI, USB, SCSI).    |
| `/sys/class/`   | Dispositivos agrupados por tipo (rede, input, tty, GPIO).    |
| `/sys/devices/` | Estrutura física real dos dispositivos.                      |
| `/sys/module/`  | Informações sobre módulos do kernel carregados.              |
| `/sys/kernel/`  | Configurações globais do kernel (ex: `uevent_helper`, `mm`). |
### **3. Diferença entre /sys/ e /proc/**

|**/sys/**|**/proc/**|
|---|---|
|Focado em **hardware e dispositivos**.|Focado em **processos e kernel**.|
|Estrutura hierárquica fixa.|Estrutura menos organizada.|
|Usado para **configurar dispositivos**.|Usado para **ler informações**.|

[[DIRETÓRIOS]]