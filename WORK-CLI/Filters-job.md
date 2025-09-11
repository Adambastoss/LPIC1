#### ``split

O comando `split` é usado para **dividir um arquivo grande em partes menores**. Isso é extremamente útil para:

#### ``split -l 15 sequencia.txt partes15_
O arquivo **sequencia.txt** tem números de 1 a 100. O comando acima divide esse arquivo em arquivos menores, cada um com uma quantidade de **15 linhas** no total.

**-l 15** - L de **lines**, 15 indica que os novos arquivos terão 15 linhas cada.  

#### ``split -b 1M arquivo_imagem.iso parte_iso_

**-b 1M** - B de **bytes** 

#### ``split -l 500 -d arquivo_de_log.txt log_parte_

**-d** - Os arquivos por padrão são criados com sufixo aa, ab, ac (**alfabéticos**).
A flag -d indica que os sufixos devem ser **numéricos** > log_parte_**00**, log_parte_**01**, log_parte_**02**...

--------------------------------------------------------------------------

#### ``tail sequencia.txt

O comando tail, ao contrário do head, mostra as **10 últimas linhas.** Uma vez que o ==head== mostra as **10 primeiras**, por padrão.
Seu uso mais clássico e poderoso é ==monitorar arquivos== de log em **tempo real**, onde novas linhas são constantemente adicionadas.

#### ``tail -n 5 sequencia.txt

**-n 5** - Mostra as últimas 5 linhas 

#### ``tail -f sequencia.txt 
Esta é a **flag mais poderosa** do `tail`. Ela não finaliza o comando após mostrar as últimas linhas; em vez disso, fica "seguindo" o arquivo, imprimindo na tela cada nova linha conforme ela é adicionada. **Essencial para monitorar logs ao vivo.** ==**-f ou --follow**==

#### ``tail -f /var/log/apache2/access.log

Uso clássico:
	Agora, qualquer **acesso novo ao servidor** web aparecerá instantaneamente no seu terminal

#### ``tail -n +20 sequencia.txt
Mostra a partir da **20º vigésima linha**.
