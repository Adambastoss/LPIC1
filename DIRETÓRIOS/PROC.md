**Sistema de arquivos virtual** (não ocupa espaço em disco, mas sim na **memória RAM**). 
/proc/ é um diretório **VOLÁTIL**, reinicia após boot.

| Entrada           | Descrição                                                              |
| ----------------- | ---------------------------------------------------------------------- |
| `/proc/cpuinfo`   | Detalhes sobre o(s) processador(es)                                    |
| `/proc/meminfo`   | Estatísticas de memória RAM                                            |
| `/proc/uptime`    | Tempo de atividade do sistema                                          |
| `/proc/version`   | Versão do kernel e informações da distribuição                         |
| /proc/filesystems | Sistemas de arquivos suportados                                        |
| /proc/dma         | **Direct Memory Access**                                               |
| /proc/interrupts  | Exibe **estatísticas em tempo real** sobre as interrupções de hardware |
| /proc/partitions  | Lista **todas as partições de disco reconhecidas pelo kernel**         |






- **DMA (Acesso Direto à Memória)** é um recurso de hardware que permite que dispositivcdos (como placas de som, controladores de disco, placas de rede) acessem a memória principal **sem a intervenção direta da CPU**, melhorando o desempenho do sistema.

[[DIRETÓRIOS]]