
O **openSUSE** utiliza o gerenciador de pacotes `zypper`

O comando **TYPE** com a flag -p mostra o **caminho absoluto** do ==executável==, ignorando aliases e funções. O comando **WHICH** também pode ser utilizado para a mesma função.

Ao usar o **System V init** , o **primeiro programa que o kernel do Linux inicia** após carregar e montar o sistema de arquivos raiz é: **==/sbin/init==**

------------------------------------------------------------------------

O comando `nohup nome-processo & ` faz com que o processo não seja finalizado mesmo após encerrar a sessão ou fechar o terminal (`nohup`). `&` faz com que o processo seja executado em **segundo plano**.
Normalmente, quando você fecha o terminal, o shell envia um sinal `SIGHUP` para todos os processos filhos — isso encerra esses processos. O `nohup` intercepta esse comportamento e **protege o processo** contra esse sinal.

------------------------------------------------------------------------
### **GREP**
Esse comando pode realizar **pesquisas** no conteúdo dos **arquivos** utilizando **expressões** **regulares**.

------------------------------------------------------------------------
Quando você cria um novo sistema de arquivos **ext4** usando o comando `mkfs.ext4`, o sistema reserva **5% do espaço total** para o usuário **root** por padrão. (Porcentagem padrão)

------------------------------------------------------------------------
### **GZIP**
padrão, o comando `gzip` ==remove== o arquivo ==original== após a compactação bem-sucedida, substituindo-o pelo arquivo comprimido com a extensão `.gz`. No entanto, existem opções para ==evitar== essa ==exclusão==: você pode usar a flag `-k` ou `gunzip -k` para manter o arquivo original, ou a opção `-c` para direcionar a saída para a tela, mantendo o arquivo original intacto.