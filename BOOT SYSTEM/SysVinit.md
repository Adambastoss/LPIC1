
Utiliza **Shell Script** para iniciar e parar os serviços. 

**/etc/init.d/** DIretório local central onde os scritps são armazenados.

Cada diretório `/etc/rcX.d/` (onde X é um número de 0 a 6) corresponde a um nível de execução diferente (runlevel). Os scripts dentro desses diretórios são, na verdade, links simbólicos para os scripts em `/etc/init.d/

##### O comando `telinit` em sistemas Linux e Unix é usado para controlar o processo de inicialização, conhecido como `init`.
Para **alternar** entre runlevels no SysVinit, utilize o comando `telinit` seguido do número do runlevel desejado. Por exemplo, para mudar para o runlevel 3, use `telinit 3`.


Qual comando no **SysVinit** é usado para **verificar** o nível de execução atual?
##### **runlevel**

No SysVinit, qual arquivo é usado para definir os níveis de execução padrão?
##### **/etc/inittab**
A linha que define o runlevel padrão no arquivo `/etc/inittab` é: `id:x:initdefault`, onde `x` representa o número do runlevel.

Qual é o comando para alterar o nível de execução no SysVinit?
##### **init**

No SysVinit, qual diretório contém os scripts de inicialização para diferentes serviços?
##### **/etc/init.d**

[[BOOT]]