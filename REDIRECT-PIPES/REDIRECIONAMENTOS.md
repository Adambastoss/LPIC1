Canal de **Entrada** (**STDIN**) - 0
Canal de **Saída** (**STDOUT**) - 1
Canal de Saída de **Erro** (**STDERR**) - 2

### **TEE**

Serve como um **T de tomada**. Lê a entrada padrão e grava simultaneamente em um ou mais arquivos.

##### EXIBIR "**Olá mundo!**" NA TELA E GRAVAR A SAÍDA NO ARQUIVO **saudacao.txt** 
``echo "Olá, mundo! | tee saudacao.txt"

##### ADICIONAR "**Nova linha**" AO FINAL DO ARQUIVO **saudacao** SEM APAGAR O CONTEÚDO ANTE...
``echo "Nova linha" | tee -a saudacao.txt

--------------------------------------------------------------------------
### **XARGS**



