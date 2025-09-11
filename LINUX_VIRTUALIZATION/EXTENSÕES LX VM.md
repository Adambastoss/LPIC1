
##### KVM (Kernel-based Virtual Machine)

Módulo do kernel Linux que o transforma em um hipervisor.

O KVM se utiliza da **virtualização assistida por hardware** (Intel VT-x ou AMD-V) para atingir um desempenho muito alto.

**`libvirt`**: Esta é uma API e um conjunto de ferramentas de gerenciamento. Ele fornece uma CLI (`virsh`) e ferramentas gráficas para gerenciar máquinas virtuais.

###### INICIAR UMA VM: ``virsh start <nome_da_vm>
###### LISTAR VMs: ``virsh list
###### PARAR VM: ``virsh shutdown <nome_da_vm>

**`QEMU`**: O **QEMU** é um ==emulador== de hardware. Ele é usado em conjunto com o KVM.
O **KVM** fornece a aceleração do ==processador==, enquanto o **QEMU** ==emula== o restante do hardware (placa de vídeo, disco rígido, placa de rede, etc.).

##### VirtIO

Ele atua como um **conjunto de drivers** e interfaces que permitem que as máquinas virtuais acessem recursos de hardware de forma eficiente, sem a necessidade de drivers específicos para cada sistema operacional convidado (guest OS)

##### SR-IOV

É uma especificação que permite que um **único dispositivo** PCI Express (PCIe), como uma placa de rede, seja *visto* como **múltiplos** **dispositivos** virtuais separados por máquinas virtuais (VMs).

Benefícios do SR-IOV:

- **Desempenho:**
    
    Redução da latência e aumento da taxa de transferência de rede em comparação com a virtualização tradicional.
    
- **Isolamento:**
    
    Cada VF tem seu próprio espaço de configuração e pode ser isolado de outras VMs.
    
- **Escalabilidade:**
    
    Permite que um único dispositivo físico seja compartilhado por várias VMs.


##### LXC 

Permite rodar múltiplos sistemas isolados no mesmo **Kernel** sem precisar de um **Hipervisor**.
Esses containers compartilham o kernel do sistema operacional hospedeiro, tornando-os mais leves e eficientes do que as máquinas virtuais tradicionais.



##### Cloud-init

O `cloud-init` é uma peça-chave na **automação** da criação de máquinas virtuais, permitindo que elas sejam configuradas de forma dinâmica e consistente na sua primeira inicialização. 

É basicamente um **script** em **YAML** que cria uma máquina já pré configurada, e esse script pode ser utilizado para criar diversas máquinas idênticas.

No arquivo */etc/cloud/==cloud.cfg*== geralmente são armazenadas configurações persistentes do `cloud-init` em uma instância baseada em Ubuntu.

### O que é o `cloud-init`?

Pense em uma máquina virtual como um "clone" de uma imagem de sistema operacional. Para ser útil, essa VM precisa ser personalizada com configurações específicas, como:

- **Nome do host**: A VM precisa de um nome único na rede.
    
- **Endereço IP e configurações de rede**: Qual IP ela vai usar? Qual gateway? Quais servidores DNS?
    
- **Chaves SSH**: Para que você possa se conectar a ela com segurança.
    
- **Usuários e senhas**: A criação de um usuário com permissões adequadas.
    
- **Instalação de pacotes**: Garantir que ferramentas essenciais (como um servidor web, por exemplo) já estejam instaladas e prontas para uso.
    
- **Execução de scripts**: Rodar comandos ou scripts de shell na primeira inicialização.


##### **cgroups**

Recurso fundamental do kernel Linux que permite **limitar, contabilizar e *isolar* o uso de recursos de um conjunto de processos**.

### Como funcionam os cgroups?

Os cgroups organizam os processos em uma **estrutura hierárquica** (como uma árvore). Cada nó nessa árvore é um grupo de controle (`cgroup`).

- **Grupos de Controle (cgroups):** Cada `cgroup` é associado a um conjunto de processos. Todos os processos em um `cgroup` estão sujeitos às mesmas regras de limitação de recursos.
    
- **Controladores (ou subsistemas):** São os módulos do kernel que gerenciam um tipo específico de recurso. Existem controladores para CPU (`cpu`), memória (`memory`), I/O de bloco (`blkio`), entre outros.
    
- **Hierarquia:** A estrutura de árvore permite que as configurações sejam herdadas. Por exemplo, se você criar um `cgroup` pai com um limite de 50% de CPU, os `cgroups` filhos dentro dele terão que compartilhar esses 50% entre si.