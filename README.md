Bem-vindo ao Projeto Linux for Newbies
O projeto é uma fonte de conhecimento abrangente sobre Linux, abordando uma variedade de tópicos essenciais para usuários e administradores de sistemas. Aqui você encontrará informações detalhadas sobre:

    Principais Comandos: Explore uma lista dos comandos mais utilizados no Linux, com explicações detalhadas de seu funcionamento e uso.

    Gerenciamento de Processos: Aprenda a controlar e monitorar processos em execução no sistema operacional Linux.

    Gerenciamento de Usuários e Permissões: Descubra como criar, modificar e gerenciar usuários, grupos e permissões de arquivo no Linux.

    Particionamento de Disco e Manutenção: Saiba como criar e gerenciar partições de disco, bem como realizar manutenção do sistema de arquivos com a ferramenta fsck e outras técnicas.

    Bibliotecas e Kernel Linux: Conheça as principais bibliotecas e o funcionamento interno do kernel do Linux.

    Redes: Explore tópicos relacionados à configuração e gerenciamento de redes no Linux, incluindo configuração de interfaces de rede e resolução de problemas de conexão.

    Gerenciamento de Pacotes: Aprenda a gerenciar pacotes de software usando ferramentas populares como apt, yum, rpm, dnf e dpkg.

    Gerenciamento de Logs: Saiba como visualizar, analisar e gerenciar logs de sistema no Linux para monitorar a saúde e o desempenho do sistema.

    Hardenning e Sistemas Linux: Descubra técnicas de hardening para fortalecer a segurança do seu sistema Linux e proteger contra ameaças.

    Gerenciamento de Boot: Entenda o processo de inicialização do sistema operacional Linux e aprenda a gerenciar o boot loader e as opções de inicialização.

### Caracter coringas

**Coringas**

```
*  - identificado nenhum, um ou mais de um carater naquela posicao
 ? - Identifica um carater naquela posicao apenas
[] - Identifica um padrao
{} - Identifica padrao de strings
^  
```

**exemplo de uso do caracter   `*`

```
ls /usr/bin/a*
 /usr/bin/a52dec
 /usr/bin/aafire
 /usr/bin/aainfo
 /usr/bin/aalib-config
 /usr/bin/aasavefont
 /usr/bin/aatest
 /usr/bin/acceleration_speed
 /usr/bin/aclocal
 /usr/bin/aclocal-1.16
 /usr/bin/addftinfo
 /usr/bin/addgnupghome
 /usr/bin/addpart
 /usr/bin/addr2line
 /usr/bin/adig
 /usr/bin/advtest
 /usr/bin/afmtodit
 /usr/bin/agetty
 /usr/bin/ahost
 /usr/bin/alacritty
```


**Veja que e possivel combinar o caracter coringas com letras**

```
ls /usr/bin/a*r
 /usr/bin/ar
 /usr/bin/aserver
 /usr/bin/asn1Parser
 /usr/bin/attr
 /usr/bin/audisp-filter
 /usr/bin/autoheader
 /usr/bin/avahi-discover
```

**exemplo de uso do caracter   `?`

```
 ls /usr/bin/m?
 /usr/bin/m4
 /usr/bin/mv
```


**buscando com 2 caracteres depois da letra m**
```
ls /usr/bin/m??
 /usr/bin/mcd -> mtools
 /usr/bin/mdu -> mtools
 /usr/bin/mev
 /usr/bin/mmd -> mtools
 /usr/bin/moc
 /usr/bin/mpc
 /usr/bin/mpd
 /usr/bin/mpv
 /usr/bin/mrd -> mtools
```


**Buscando com 2 coringas **

```
ls a?t*
 aatest
 artist_to_albumartist
 attr
 autoconf
 autoheader
 autom4te
 automake
 automake-1.16
 autopoint
 autoreconf
 autoscan
 autoupdate
 avtest
```



**exemplo de uso do caracter   `[ ]`
lista todos que comecao com a letra m e depois vem da letra a ate z

```
 ls /usr/bin/m[a-z]
 /usr/bin/mv
```

**entendendo o caracter** `^`
o caracter ^ indica que tudo que vier depois dele sera ignorado.

exemplo :
```
 ls m[^abc]
 m4
 mv
```

```
ls m[^a-c]
 m4
 mv
```

```
ls m[^t-v]
 m4
```

**Exemplo de uso do caracter   `{ }`

```
ls x{zd,ze}*
 xzdec
 xzdiff
 xzegrep -> xzgrep
```

*repare que dentro dos conchetes tem as strings `zd,ze` o que significa quer que faco um busca que comece com x depois vem com as letras zm e ze.*

| Comando           | Descrição                                                                                                                                           |
| ----------------- | --------------------------------------------------------------------------------------------------------------------------------------------------- |
| `date`            | Mostra a data e hora atuais.                                                                                                                        |
| `date -u`         | Mostra a data e hora atuais no Tempo Universal Coordenado (UTC), independente de fuso horário.                                                     |
| `date -s 08:43`   | Altera manualmente a hora do sistema para 08h43min.                                                                                                 |
| `date 101007452020` | Altera manualmente a data e hora para 10 de outubro de 2020, às 07:45. Este formato é: MMDDhhmmYYYY (Mês, Dia, Hora, Minuto, Ano).               |
| `hwclock --systohc` | Sincroniza o relógio do sistema com o relógio da BIOS.                                                                                             |
| `date +%d`        | Mostra o dia atual do mês.                                                                                                                          |
| `date +%d-%y`     | Mostra o dia e o ano atuais no formato "dia-ano" (dois dígitos para o dia e dois dígitos para o ano).                                               |
| `clear`           | Limpa a tela do terminal, removendo o conteúdo anterior.                                                                                            |
| `%y`              | Representa o ano em formato curto, com apenas os dois últimos dígitos. Por exemplo, "22" para 2022.                                                 |
| `%Y`              | Representa o ano por extenso, com quatro dígitos. Por exemplo, "2022".                                                                              |
| `%T`              | Representa a hora no formato "HH:MM:SS". Por exemplo, "14:30:00".                                                                                   |
| `%j`              | Representa o número do dia do ano, variando de 001 a 366, dependendo do ano bissexto. Por exemplo, "152" para o dia 152 do ano.                     |

```bash
❯ date +%d-%m-%Y

29-04-2024
```

## Comando df
Claro! O comando `df` (abreviação de "disk free") é uma ferramenta de linha de comando em sistemas Unix e Unix-like, como Linux, que é usada para exibir informações sobre o espaço em disco utilizado e disponível nos sistemas de arquivos.

Quando você executa o comando `df` sem argumentos adicionais, ele mostra uma lista de todos os sistemas de arquivos atualmente montados no sistema, juntamente com várias informações relacionadas ao uso do espaço em disco, incluindo:

- O ponto de montagem do sistema de arquivo.
- O tipo de sistema de arquivo.
- O tamanho total do sistema de arquivo.
- O espaço usado.
- O espaço livre.
- O uso percentual do espaço disponível.

Por exemplo, a saída pode se parecer com isto:

```
Filesystem     1K-blocks    Used Available Use% Mounted on
/dev/sda1       12345678 1234567  9876543  12% /
/dev/sdb1       87654321 4567890 76543210   6% /home
```

Neste exemplo, `/dev/sda1` e `/dev/sdb1` são dispositivos de armazenamento, com `/dev/sda1` montado como raiz (`/`) e `/dev/sdb1` montado em `/home`. Os números representam o tamanho total, o espaço utilizado, o espaço livre e a porcentagem de uso, respectivamente.

Você também pode usar opções adicionais com o comando `df` para personalizar a saída ou filtrar os resultados, como `-h` para mostrar tamanhos em unidades legíveis por humanos (KB, MB, GB, etc.), `-T` para exibir o tipo de sistema de arquivo e outras opções.


| Comando      | Descrição                                                                                                         |
| ------------ | ----------------------------------------------------------------------------------------------------------------- |
| `df -h`      | Exibe o uso de disco em unidades legíveis por humanos (MB, GB, etc.), formatando para ser mais fácil de entender. |
| `df -H`      | Formata o uso de disco em unidades comerciais (por exemplo, 1GB = 1000MB).                                        |
| `df -l`      | Mostra apenas os sistemas de arquivos locais, excluindo aqueles montados via rede.                                |
| `df -m`      | Define a saída em megabytes.                                                                                      |
| `df -a`      | Inclui os pseudo-filesystems na saída, como `/proc`, `/sys`, etc.                                                 |
| `df -i`      | Mostra a saída com o número de inodes (índices dos arquivos) dos pontos de montagem.                              |
| `df -T`      | Mostra o tipo de sistema de arquivo usado em cada partição.                                                       |
| `df -t ext4` | Exibe a saída apenas para sistemas de arquivos do tipo ext4.                                                      |

### Comando ln

Ocomando `ln` para criar links, tanto um hard link quanto um link simbólico (soft link).

- O comando `ln /bin/ls ls` cria um hard link chamado `ls` para o arquivo `/bin/ls`, o que significa que agora você tem um novo nome (`ls`) que aponta para o mesmo conteúdo do arquivo `/bin/ls`. Isso não cria uma cópia do arquivo; ambos os nomes referem-se ao mesmo arquivo no sistema de arquivos.

- O comando `ln -s /bin/ls ls-link` cria um link simbólico (soft link) chamado `ls-link` que aponta para o arquivo `/bin/ls`. Este tipo de link é um atalho para o arquivo original, semelhante a um atalho em sistemas operacionais Windows. Se você acessar `ls-link`, estará indiretamente acessando `/bin/ls`.

Assim, você criou um hard link chamado `ls` para `/bin/ls` e um link simbólico chamado `ls-link` que aponta para `/bin/ls`. Isso pode ser útil para acessar o comando `ls` de diferentes maneiras no sistema.


*Curiosidade : ao usar o comando `cp -l` ele copiara os arquivos usando hardlink*

Aqui está a tabela formatada com as características do hard link e do link simbólico:

| Característica        | Hard Link                                                                                   | Link Simbólico                                                                      |
|-----------------------|---------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------|
| Referência para inode | Direta para o inode do arquivo original                                                     | Referência para o caminho do arquivo original                                        |
| Localização           | Todos os hard links e o arquivo original estão no mesmo sistema de arquivos                | Pode atravessar sistemas de arquivos, apontando para arquivos em diferentes dispositivos |
| Atualizações          | Alterações no arquivo original são refletidas em todos os hard links                        | Se o arquivo original for excluído ou movido, o link simbólico se torna inútil        |
| Tamanho               | Não adiciona sobrecarga de tamanho ao sistema de arquivos                                   | Adiciona um tamanho extra ao sistema de arquivos, armazenando o caminho completo do arquivo original |
| Permissões            | Compartilha as mesmas permissões e atributos do arquivo original                            | As permissões do link simbólico são independentes das do arquivo original              |


#### Comando du

Aqui está uma tabela simplificada explicando os diferentes usos do comando `du` para exibir o tamanho de arquivos e diretórios:

| Comando     | Descrição                                                                       |
|-------------|---------------------------------------------------------------------------------|
| `du -h`     | Exibe o tamanho de arquivos e diretórios em unidades legíveis por humanos (KB, MB, etc.), usando blocos de 1024 bytes. |
| `du -H`     | Exibe o tamanho de arquivos e diretórios em unidades legíveis por humanos, usando blocos de 1000 bytes. |
| `du -s`     | Apresenta apenas o tamanho total utilizado, sem listar os tamanhos individuais dos arquivos e diretórios. |
| `du -k`     | Mostra o tamanho em kilobytes (KB).                                           |
| `du -m`     | Mostra o tamanho em megabytes (MB).                                            |
| `du --inodes` | Exibe a contagem de inodes (número de entradas de arquivo) em vez do tamanho. |
| `du -c`     | Adiciona uma linha final que mostra o total de todos os arquivos e diretórios listados. |
Esses comandos são úteis para entender a ocupação de espaço em disco por arquivos e diretórios no sistema.
#### Comando find
Aqui está a tabela formatada com os parâmetros e exemplos de uso do comando `find`:

| Parâmetro           | Descrição                                                                                                                                      | Exemplo                                                              |
|---------------------|------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| `-name`             | Procura por arquivos ou diretórios com um nome específico.                                                                                     | `find /usr -name "mc"`                                              |
| `--maxdepth`        | Define a profundidade máxima para a busca de diretórios.                                                                                       | `find /usr -maxdepth 4 -type f -name "mc"`                          |
| `--mindepth`        | Define a profundidade mínima para a busca de diretórios.                                                                                       | `find /usr -mindepth 3 -type f -name "mc"`                          |
| `-type`             | Filtra por tipo de arquivo ou diretório.                                                                                                       | `find /usr -type f -name "mc"`                                      |
| `-ctime`            | Filtra por arquivos que foram criados há n dias.                                                                                                | `find /usr -ctime 3 -type f`                                        |
| `-mtime`            | Filtra por arquivos que foram modificados há n dias.                                                                                            | `find /usr -mtime 3 -type f`                                        |
| `-atime`            | Filtra por arquivos que foram acessados há n dias.                                                                                              | `find /usr -atime 3 -type f`                                        |
| `-cmin`             | Filtra por arquivos que foram criados há n minutos.                                                                                            | `find /usr -cmin -30 -type f`                                       |
| `-mmin`             | Filtra por arquivos que foram modificados há n minutos.                                                                                         | `find /usr -mmin -30 -type f`                                       |
| `-amin`             | Filtra por arquivos que foram acessados há n minutos.                                                                                           | `find /usr -amin -30 -type f`                                       |
| `-gid`              | Filtra por arquivos pertencentes ao GID especificado.                                                                                           | `find /usr -gid 1001 -type f`                                       |
| `-uid`              | Filtra por arquivos pertencentes ao UID especificado.                                                                                           | `find /usr -uid 1001 -type f`                                       |
| `-user`             | Filtra por arquivos pertencentes ao usuário especificado.                                                                                        | `find /usr -user username -type f`                                  |
| `-group`            | Filtra por arquivos pertencentes ao grupo especificado.                                                                                         | `find /usr -group groupname -type f`                                |
| `-links`            | Filtra por arquivos com o número especificado de links.                                                                                         | `find /usr -links 2 -type f`                                        |
| `-size`             | Filtra por arquivos com um tamanho específico.                                                                                                  | `find /usr -size +1000k -type f`                                   |
| `-type`             | Filtra por tipo de arquivo.                                                                                                                     | `find /usr -type f -name "mc"`                                      |

#### Comando free

Aqui está a explicação das métricas de memória e um exemplo formatado em tabela:

| Métrica          | Descrição                                                                                                                             | Exemplo             |
|------------------|---------------------------------------------------------------------------------------------------------------------------------------|---------------------|
| **Total**        | Representa a quantidade total de memória disponível no sistema.                                                                      | 8 GB                |
| **Used**         | Indica a quantidade de memória atualmente em uso pelo sistema.                                                                       | 4 GB                |
| **Free**         | Refere-se à quantidade de memória disponível e não utilizada no momento.                                                             | 2 GB                |
| **Shared Buff/Cache** | Representa a quantidade de memória compartilhada para acelerar operações do sistema, incluindo cache e buffer.                   | 2 GB                |

Exemplo formatado em tabela:

| Métrica           | Quantidade |
| ----------------- | ---------- |
| Total             | 8 GB       |
| Used              | 4 GB       |
| Free              | 2 GB       |
| Shared Buff/Cache | 2 GB       |

1. **Mostrar em kilobytes:**
```bash
free --killo
```
Este comando mostra a saída em kilobytes.

2. **Mostrar em megabytes:**
```bash
free --mega
```
Este comando mostra a saída em megabytes.

3. **Usar o padrão de 1024 (kibi):**
```bash
free --kibi
```
Este comando utiliza o padrão de 1024 para representar os valores.

4. **Padrão de 1024 para megabytes (mebi):**
```bash
free --mebi
```
Este comando utiliza o padrão de 1024 para representar os valores em megabytes.

5. **Mostrar em gigabytes:**
```bash
free --giga
```
Este comando mostra a saída em gigabytes.

6. **Padrão de 1024 para gigabytes**
```bash
free --gibi
```
Este comando utiliza o padrão de 1024 para representar os valores em gigabytes.

7. **Mostra o padrao em megabytes em um intervalo de tempo**
```shell
free --mega -s 1
```
Este comando utiliza o padrão de mega monstrando a saida a cada 1 segundo

O comando `free` obtém as informações sobre o uso da memória diretamente do arquivo `/proc/meminfo`. Ele usa esses dados para apresentar as estatísticas de memória no sistema de forma mais acessível e compreensível.


#### Comando grep
Aqui está uma tabela formatada com os parâmetros e exemplos de uso do comando `grep`:

| Parâmetro | Descrição                                                                                       | Exemplo                         |
| --------- | ----------------------------------------------------------------------------------------------- | ------------------------------- |
| `-v`      | Inverte a busca, mostrando linhas que não correspondem ao padrão especificado.                  | `grep -v "pattern" file.txt`    |
| `-f`      | Permite buscar por padrões em um arquivo usando expressões fornecidas em outro arquivo.         | `grep -f patterns.txt file.txt` |
| `-i`      | Ignora diferenças entre maiúsculas e minúsculas durante a busca.                                | `grep -i "pattern" file.txt`    |
| `-E`      | Realiza a pesquisa por expressões regulares, interpretando o padrão como uma expressão regular. | `grep -E "pattern" file.txt`    |
| `-F`      | Realiza a pesquisa por caracteres exatos, sem interpretá-los como expressões regulares.         | `grep -F "pattern" file.txt`    |
| `-r`      | Realiza uma pesquisa de forma recursiva.                                                        | `grep -r "pattern" directory`   |
| `-h`      | Oculta o nome dos arquivos.                                                                     | `grep -h "pattern" file.txt`    |
| `-l`      | Lista somente o nome dos arquivos.                                                              | `grep -l "pattern" file.txt`    |
| `-n`      | Retorna o número da linha do arquivo que contém a expressão.                                    | `grep -n "pattern" file.txt`    |


Exemplo:

```shell
grep -iE '^www-data.*nologin$' /etc/passwd
```

Neste exemplo, o comando `grep` é usado para buscar no arquivo `/etc/passwd` linhas que começam com "www-data" e terminam com "nologin", ignorando diferenças entre maiúsculas e minúsculas. O caractere `^` indica o início da linha e `$` indica o final da linha.

#### Comando head

Aqui está uma tabela formatada com os parâmetros e exemplos de uso do comando `head`:

| Parâmetro      | Descrição                                                                                           | Exemplo                                                              |
|----------------|-----------------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| `-n`           | Exibe o número especificado de linhas.                                                             | `head -n 5 file.txt`                                                 |
| `-c`           | Exibe o número especificado de bytes.                                                              | `head -c 100 file.txt`                                               |

Exemplo:

```shell
head -n 5 file.txt
```

Neste exemplo, o comando `head` é usado para exibir as primeiras 5 linhas do arquivo `file.txt`.


#### Comando more
O comando `more` é utilizado no terminal do Unix/Linux para visualizar o conteúdo de um arquivo de texto, mas de forma paginada, o que significa que ele exibe uma página por vez. Isso é útil especialmente para arquivos longos, já que permite visualizar o conteúdo de forma mais organizada e controlada.

Quando você utiliza o comando `more`, o arquivo é exibido página por página e você pode navegar pelas páginas pressionando a tecla Espaço para avançar para a próxima página, a tecla Enter para avançar uma linha por vez ou a tecla Q para sair do visualizador.

Por exemplo, para visualizar o conteúdo de um arquivo chamado `exemplo.txt`, você pode usar o seguinte comando:

```
more exemplo.txt
```

Isso exibirá o conteúdo do arquivo `exemplo.txt` uma página por vez, permitindo que você o leia de forma mais fácil.



#### Comando less

O comando `less` é uma versão mais avançada do comando `more`. 
Algumas das principais características do `less` incluem:

1. **Navegação bidirecional**: Além de rolar para frente através das páginas do arquivo, você também pode rolar para trás, o que não é possível com o `more`.

2. **Pesquisa**: Você pode pesquisar por texto dentro do arquivo pressionando `/` seguido do termo de pesquisa e pressionando Enter. O `less` destacará todas as ocorrências encontradas.

3. **Avanço e retrocesso por linhas**: Além de avançar e retroceder por páginas, você também pode rolar uma linha por vez para cima ou para baixo usando as teclas de seta ou as teclas Page Up e Page Down.

4. **Visualização de números de linha**: Por padrão, o `less` exibe os números de linha à esquerda, o que pode ser útil para referência.

Para usar o `less`, basta digitar `less` seguido do nome do arquivo que você deseja visualizar. Por exemplo:

```
less exemplo.txt
```

Depois de abrir o arquivo com o `less`, você pode usar as teclas de navegação e pesquisa mencionadas anteriormente para interagir com o conteúdo do arquivo. Quando terminar de visualizar o arquivo, você pode pressionar `q` para sair do `less` e voltar ao prompt do terminal.


####  Comando sort

**Exemplo do comando sort**

```
sort list.txt 
```

```
sort lista.txt
1
1
10
100
1000
11
50
Gleydson
Guiafoca
Jeferson
Linux
giropops
```

Aqui está uma tabela formatada com os parâmetros e exemplos de uso do comando `sort`:

| Parâmetro      | Descrição                                                                                           | Exemplo                                                              |
|----------------|-----------------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| `-r`           | Inverte a ordem da classificação da listagem.                                                      | `sort -r file.txt`                                                   |
| `-n`           | Classifica em ordem numérica.                                                                      | `sort -n file.txt`                                                   |
| `-c`           | Verifica se a lista está ordenada e retorna se está ordenada ou desordenada.                       | `sort -c lista.txt`                                                  |
| `-(n)`         | Usa uma numeração de colunas baseada em zero para especificar a coluna a ser ordenada.             | `sort -t: -k2 -n file.txt`                                          |
| `-t`           | Define um delimitador para a ordenação.                                                            | `sort -t"," -k3 file.csv`                                           |
| `-k` `(n)`     | Usa uma numeração de colunas baseada em um para especificar a coluna a ser ordenada.               | `sort -k2 file.txt`                                                  |

Exemplos:

```shell
sort -r file.txt
sort -n file.txt
sort -c lista.txt
sort -t: -k2 -n file.txt
sort -t"," -k3 file.csv
sort -k2 file.txt
```

Esses exemplos demonstram como usar o comando `sort` com diferentes opções para classificar e ordenar arquivos de texto.

###### Entendendo o sort -c 

No comando

```shell
sort lista.txt | sort -n -c
```

o segundo `sort -n -c` não garante que a lista esteja ordenada numericamente porque o primeiro `sort` não foi especificado para ordenar numericamente. O `sort -n -c` simplesmente verifica se a lista está ordenada numericamente, mas não a ordena numericamente antes disso.

A correção para esse exemplo seria:

```shell
sort -n lista.txt | sort -n -c
```

Aqui, o primeiro `sort -n` ordena numericamente a lista antes de passá-la para o segundo `sort -n -c`, que então verifica se está ordenada numericamente.

##### Entendendo sort por colunas

Ao usar o comando `sort` sem especificar uma coluna específica, ele irá ordenar os itens da lista considerando a primeira coluna como padrão. Isso é equivalente a especificar `sort +0`, onde a numeração das colunas começa em zero.

Para ordenar pela segunda coluna, podemos utilizar `sort +1`, considerando que a numeração das colunas segue a lógica de 0 para a primeira coluna, 1 para a segunda, e assim por diante:

```shell
cat lista_nova.txt | sort +1
Jeferson Fernando
Guia Foca
Vai LinuxTips
Gleydson Mazioli
LinuxTips Vai!
```

Podemos também utilizar um delimitador para definir onde as colunas começam e terminam. Por exemplo, ao definir "F" como delimitador, o `sort` entenderá que tudo antes da letra "F" pertence à primeira coluna (0), e tudo após a letra "F" pertence à segunda coluna (1):

```shell
cat lista_nova.txt | sort +1 -t "F"
Gleydson Mazioli
LinuxTips Vai!
Vai LinuxTips
Jeferson Fernando
Guia Foca
```

Além disso, o comando `sort -k` é similar ao `sort +n`, mas com a numeração das colunas começando em 1. Por exemplo, para ordenar pela primeira coluna, usaríamos:

```shell
cat lista_nova.txt | sort -k 1
Gleydson Mazioli
Guia Foca
Jeferson Fernando
LinuxTips Vai!
Vai LinuxTips
```

Substituindo o "1" por "2", poderíamos ordenar pela segunda coluna, e assim por diante.

#### Comando tail
O comando `tail` é usado para visualizar o final de um arquivo, o que é semelhante ao comando `head`, que permite visualizar as primeiras linhas. Enquanto o `head` exibe as 10 primeiras linhas por padrão, o `tail` exibe as 10 últimas linhas por padrão.

| Parâmetro       | Descrição                                                                                                         | Exemplo                               |
|-----------------|-------------------------------------------------------------------------------------------------------------------|---------------------------------------|
| `tail <arquivo>`| Mostra as últimas 10 linhas do arquivo.                                                                          | `tail file.txt`                       |
| `tail -n <número>` | Define o número de linhas a serem mostradas na saída do comando.                                                 | `tail -n 20 file.txt`                |
| `tail -f`       | Mostra as últimas linhas do arquivo em tempo real, útil para visualizar atualizações recentes, como logs em tempo real. | `tail -f logfile.txt`                |

#### Comando Time

O time e um comando de retorno o tempo de execucao de um comando

```shell
time <comando> 

root@DebianServer:/home/bless# time ls

real	0m0.004s
user	0m0.001s
sys	0m0.004s
root@DebianServer:/home/bless# 
```


#### Comando touch

Aqui está a tabela formatada com os comandos e suas descrições:

| Comando                   | Descrição                                                                                                        |
|---------------------------|------------------------------------------------------------------------------------------------------------------|
| `touch <nome do arquivo>` | Cria um novo arquivo vazio com o nome especificado.                                                             |
| `touch -t mmddhhmm <arquivo>` | Modifica a data e hora de modificação do arquivo para a data e hora especificadas.                               |
| `touch -a -t`             | Modifica o tempo de acesso do arquivo para a data e hora especificadas.                                         |

Exemplo:

```shell
touch -t 10120815 arquivo
ls -la arquivo
```

Neste exemplo, o comando `touch -t 10120815 arquivo` é usado para modificar a data do arquivo chamado "arquivo" para 12 de outubro de 2024 às 08:15. Em seguida, o comando `ls -la arquivo` é usado para exibir as informações detalhadas do arquivo, mostrando a data e hora modificadas.


##### Comando uptime

O comando `uptime` exibe o tempo de funcionamento do sistema desde o último reinício, além de mostrar a carga média do sistema nas últimas 1, 5 e 15 minutos.

Por exemplo:
```
14:27:42 up 12 days,  2:03,  1 user,  load average: 0.00, 0.01, 0.05
```

Isso indica que o sistema está funcionando há 12 dias e 2 horas desde o último reinício, há um usuário conectado e a carga média do sistema é 0.00, 0.01 e 0.05 para os últimos 1, 5 e 15 minutos, respectivamente.

##### Comando dmesg
Aqui está uma tabela formatada com os parâmetros e descrições do comando `dmesg`:

| Comando                   | Descrição                                                                                                 |
|---------------------------|-----------------------------------------------------------------------------------------------------------|
| `dmesg -t`                | Retorna mensagens sem o timestamp.                                                                         |
| `dmesg --color=never`     | Retorna mensagens sem cor.                                                                                 |
| `dmesg --color=auto`      | Retorna mensagens com cor.                                                                                 |
| `dmesg -w`                | Similar ao `tail -f`, mostra as últimas linhas do `dmesg` em tempo real.                                    |
| `dmesg -T`                | Transforma o timestamp do boot para data/hora legível.                                                     |
| `dmesg -c`                | Limpa as mensagens do buffer do kernel.                                                                   |

Esses comandos são úteis para visualizar mensagens do kernel, e os parâmetros podem ser combinados para obter diferentes tipos de saída, como visualização em tempo real, limpeza do buffer do kernel e formatação dos timestamps.

##### Comando echo
O comando echo imprime uma mensagem na tela

```shell
echo -n = suprime a quebra de linha
echo -e = ativa a interpretação de caracteres especiais.

```


##### Comando su

O comando su permite elevar os privilegios de usuarios comuns para o usuario root

| Comando                        | Descrição                                                                                                        |
|--------------------------------|------------------------------------------------------------------------------------------------------------------|
| `su`                           | Permite que um usuário comum eleve seus privilégios para o usuário root, exigindo a senha do root.             |
| `su -`                         | Loga como root, eliminando todas as variáveis de ambiente e iniciando um ambiente completamente novo, tornando uma prática mais segura. |
| `su - <user> -s /bin/bash`     | Loga como o usuário especificado com o shell `/bin/bash`, permitindo especificar outro shell, se necessário.    |

Esses são os comandos e suas descrições relacionadas ao comando `su`, que é usado para elevar os privilégios de um usuário comum para o usuário root no sistema.
#### Comando sudo

O comando "sudo" também possibilita a elevação de privilégios para o superusuário. Sua vantagem está em permitir especificar quais usuários podem elevar seus privilégios para o root, adicionando-os ao grupo "sudo".

| Comando                    | Descrição                                                                                                  |
|----------------------------|------------------------------------------------------------------------------------------------------------|
| `adduser <user> sudo`      | Adiciona um usuário ao grupo "sudo", concedendo-lhe permissões para executar comandos com privilégios de root. |
| `deluser <user> sudo`      | Remove um usuário do grupo "sudo", revogando suas permissões para executar comandos com privilégios de root. |
| `sudo su`                  | Faz login como usuário root usando as credenciais do usuário atual.                                        |

Esses comandos são úteis para gerenciar as permissões de usuários e grupos no sistema Linux, permitindo que os usuários comuns executem comandos com privilégios de root através do `sudo`.


#### Comando sync

*O comando "sync" permite que os buffers (cache de dados a serem gravados na memória) sejam sincronizados e escritos do kernel para o disco.*


#### comando uname
O comando "uname" exibe informações sobre o sistema operacional. Ele pode fornecer detalhes como o nome do kernel, a versão, o tipo de hardware e outras informações relacionadas ao sistema.

| Comando         | Descrição                                                                                                      |
|-----------------|----------------------------------------------------------------------------------------------------------------|
| `uname -a`      | Retorna informações completas do sistema operacional, incluindo nome e versão do kernel, arquitetura e compilação. |
| `uname -s`      | Exibe o nome do kernel.                                                                                       |
| `uname -n`      | Mostra o nome da máquina na rede (hostname).                                                                  |
| `uname -r`      | Apresenta a versão atual do kernel.                                                                           |
| `uname -v`      | Indica a data em que o kernel foi compilado.                                                                  |
| `uname -m`      | Informa a arquitetura utilizada no kernel.                                                                    |

Esses comandos são úteis para obter informações sobre o kernel e o sistema operacional em sistemas Unix-like, como Linux e macOS.

#### Comando reboot
O comando reboot basicamente reinicia a maquina

Aqui está a tabela formatada com os comandos e suas descrições:

| Comando                           | Descrição                                                                                                            |
|-----------------------------------|----------------------------------------------------------------------------------------------------------------------|
| `systemctl reboot`                | Reinicia o sistema usando o comando systemctl, outra sintaxe para o comando "reboot".                                 |
| `reboot -f`                       | Reinicia o sistema forçadamente, sem fechar os programas primeiro.                                                    |
| `shutdown -r now`                 | Reinicia o sistema usando o comando "shutdown".                                                                       |
| `echo b > /proc/sysrq-trigger`    | Reinicia o sistema interagindo diretamente com o kernel, escrevendo 'b' no arquivo `/proc/sysrq-trigger`.             |

###### comando halt

O comando halt  basicamente reinicia a maquina

Aqui está a tabela formatada com os comandos e suas descrições:

| Comando                                | Descrição                                                                                                               |
|----------------------------------------|-------------------------------------------------------------------------------------------------------------------------|
| `halt`                                 | Desliga o sistema imediatamente.                                                                                        |
| `systemctl halt`                       | Outra forma de desligar o sistema usando o comando systemctl.                                                          |
| `shutdown -h now`                      | Desliga o sistema imediatamente usando o comando "shutdown".                                                            |
| `echo o > /proc/sysrq-trigger`         | Desliga o sistema interagindo diretamente com o kernel, escrevendo 'o' no arquivo `/proc/sysrq-trigger`.               |
| `shutdown -h <horário>`                | Agenda o desligamento da máquina para um horário específico. Por exemplo, `shutdown -h 09:40`.                       |
| `shutdown -h +10`                      | Desliga a máquina em 10 minutos a partir do momento em que o comando é executado.                                      |
| `shutdown -c`                          | Cancela o desligamento ou reinício agendado.                                                                           |

###### Comando wc
O comando "wc" é usado para contar o número de palavras, bytes e linhas em um arquivo ou na entrada padrão.

```shell
❯ wc /etc/passwd
  31   68 1697 /etc/passwd
```

*1697 - o tamanho do arquivo*

*31   - numero de linhas dos arquivo*

*68  -  numero de palavras dentro do arquivo*

| Comando    | Descrição                                          |
|------------|----------------------------------------------------|
| `wc -l`    | Retorna o número de linhas no arquivo.             |
| `wc -c`    | Retorna o número de bytes no arquivo.              |
| `wc -w`    | Retorna o número de palavras no arquivo.           |

Esses são os parâmetros mais comuns do comando `wc`, que são úteis para contar o número de linhas, bytes e palavras em um arquivo.
###### Comando seq


```
seq 10
```
- Enumera a sequência de 1 até 10.

```
seq 2 10
```
- Enumera a sequência de 2 até 10.

```
seq 2 2 10
```
- Inicia a partir do número 2, avançando de 2 em 2 até o número 10. O segundo "2" representa o intervalo entre os números.

```
seq -w 15
```
- O comando "seq -w" é utilizado para imprimir uma sequência de números com preenchimento de zeros à esquerda.

##### Comando chattr

Claro, aqui está uma explicação mais detalhada e algumas correções:

O comando `chattr` no Linux é usado para alterar os atributos do sistema de arquivos, incluindo diretórios e arquivos. Você também pode listar esses atributos usando o comando `lsattr`.

### Lista de Atributos:

- **`+i`**: Adiciona o atributo "imutável", impedindo que o arquivo seja alterado, renomeado ou excluído, mesmo por usuários com permissões de superusuário (root). Por exemplo:
  ```
  chattr +i arquivo
  ```
- **`-i`**: Remove o atributo "imutável" de um arquivo ou diretório.

- **`+a`**: Adiciona o atributo "append-only" (somente adicionar), permitindo que novos dados sejam adicionados ao arquivo, mas não permitindo alterações nos dados existentes ou remoção do arquivo.

- **`-a`**: Remove o atributo "append-only" de um arquivo ou diretório.

- **`+R`**: Aplica as alterações recursivamente em diretórios e seus conteúdos.

- **`=aie`**: Adiciona os atributos "append-only" e "imutável" simultaneamente.
 
- **`+c`**:O atributo "+c" no comando `chattr` do Linux é usado para habilitar ou desabilitar a compressão de dados no arquivo ou diretório especificado. Quando o atributo "+c" é definido para um arquivo, ele indica que o conteúdo do arquivo deve ser compactado automaticamente pelo sistema de arquivos quando possível.

- `+s`:O atributo "+s" no comando `chattr` do Linux é usado para definir o atributo "secure deletion" (exclusão segura) em arquivos ou diretórios

- `+S`: sysnc de de forma imediata, em outras palavras(Esse atributo especifica que novas alocações de blocos de disco para arquivos dentro desse diretório devem ser feitas de forma a otimizar a busca no diretório.)

- `-D`: Realiza a sincronização imediata em diretórios, similar à função do `+S`.

### Exemplo de Uso:

Suponha que você tenha um arquivo chamado "teste" e deseje torná-lo imutável para evitar modificações acidentais ou maliciosas:

1. Visualize os atributos atuais do arquivo usando `lsattr`:
   ```
   lsattr teste
   ----i--------e---- teste
   ```

2. Para adicionar o atributo "imutável" ao arquivo:
   ```
   chattr +i teste
   ```

3. Agora, tente remover ou modificar o arquivo:
   ```
   rm -f teste
   # Resultará em: Operation not permitted

   echo "Nova linha" >> teste
   # Resultará em: Operation not permitted
   ```

4. Para remover o atributo "imutável" do arquivo:
   ```
   chattr -i teste
   ```

Após isso, você poderá remover ou modificar o arquivo normalmente.

Esses comandos são úteis em situações onde você deseja proteger arquivos críticos ou diretórios importantes contra alterações não autorizadas.

```
lsattr
--------------e------- ./rust
--------------e------- ./Shell
--------------e------- ./desec
--------------e------- ./web
----i---------e------- ./teste
--------------e------- ./python
```

#### Comando cut

O comando `cut` é uma ferramenta muito útil em sistemas baseados em Unix/Linux para cortar (ou extrair) partes específicas de linhas de texto de arquivos ou da entrada padrão. Ele é frequentemente usado para cortar colunas de texto de arquivos de texto delimitados por espaço ou tabulação. 

Por exemplo, suponha que temos um arquivo chamado `dados.txt` com o seguinte conteúdo:

```
João Silva 30
Maria Souza 25
Carlos Santos 35
```

Se quisermos extrair apenas os nomes das pessoas desse arquivo, podemos usar o `cut` da seguinte forma:

```bash
cut -d ' ' -f 1,2 dados.txt
```

Neste comando, `-d ' '` especifica que o delimitador é um espaço em branco, e `-f 1,2` indica que queremos cortar a primeira e a segunda colunas do arquivo.

Isso resultaria na saída:

```
João Silva
Maria Souza
Carlos Santos
```

```
cut

cut -d ":" = informa o delimitador por exemplo o delimitor sera o : .
-f  =  especifica qual coluna/campo quer extrair do arquivo.
-b  = saída dos bytes
-c  = saida de caracteres

```

```
cut -d ":" -f 1 /etc/passwd
root
bin
daemon
mail
ftp
http
nobody
dbus
systemd-coredump
systemd-network
systemd-oom
systemd-journal-remote
systemd-resolve
systemd-timesync
tss
uuidd
dhcpcd
bless
avahi
polkitd
git
geoclue
rtkit
sddm
flatpak
mpd
qemu
brltty
gluster
rpc
openvpn
nm-openvpn
```


*"Também podemos trazer duas colunas, separadas por vírgula."*

```
❯ cut -d ":" -f 1,7 /etc/passwd

root:/usr/bin/bash
bin:/usr/bin/nologin
daemon:/usr/bin/nologin
mail:/usr/bin/nologin
ftp:/usr/bin/nologin
http:/usr/bin/nologin
nobody:/usr/bin/nologin
dbus:/usr/bin/nologin
systemd-coredump:/usr/bin/nologin
systemd-network:/usr/bin/nologin
systemd-oom:/usr/bin/nologin
systemd-journal-remote:/usr/bin/nologin
systemd-resolve:/usr/bin/nologin
systemd-timesync:/usr/bin/nologin
tss:/usr/bin/nologin
uuidd:/usr/bin/nologin
dhcpcd:/usr/bin/nologin
bless:/usr/bin/zsh
avahi:/usr/bin/nologin
polkitd:/usr/bin/nologin
git:/usr/bin/git-shell
geoclue:/usr/bin/nologin
rtkit:/usr/bin/nologin
sddm:/usr/bin/nologin
flatpak:/usr/bin/nologin
mpd:/usr/bin/nologin
qemu:/usr/bin/nologin
brltty:/usr/bin/nologin
gluster:/usr/bin/nologin
rpc:/usr/bin/nologin
openvpn:/usr/bin/nologin

```

*Também podemos estabelecer um intervalo.*


```
cut -d ":" -f 1-3,7 /etc/passwd

root:x:0:/usr/bin/bash
bin:x:1:/usr/bin/nologin
daemon:x:2:/usr/bin/nologin
mail:x:8:/usr/bin/nologin
ftp:x:14:/usr/bin/nologin
http:x:33:/usr/bin/nologin
nobody:x:65534:/usr/bin/nologin
dbus:x:81:/usr/bin/nologin
systemd-coredump:x:980:/usr/bin/nologin
systemd-network:x:979:/usr/bin/nologin
systemd-oom:x:978:/usr/bin/nologin
systemd-journal-remote:x:977:/usr/bin/nologin
systemd-resolve:x:976:/usr/bin/nologin
systemd-timesync:x:975:/usr/bin/nologin
tss:x:974:/usr/bin/nologin
uuidd:x:68:/usr/bin/nologin
dhcpcd:x:973:/usr/bin/nologin
bless:x:1000:/usr/bin/zsh
avahi:x:972:/usr/bin/nologin
polkitd:x:102:/usr/bin/nologin
git:x:971:/usr/bin/git-shell
geoclue:x:969:/usr/bin/nologin
rtkit:x:133:/usr/bin/nologin
sddm:x:968:/usr/bin/nologin
flatpak:x:967:/usr/bin/nologin
mpd:x:45:/usr/bin/nologin
qemu:x:966:/usr/bin/nologin
brltty:x:964:/usr/bin/nologin
gluster:x:963:/usr/bin/nologin
rpc:x:32:/usr/bin/nologin
openvpn:x:962:/usr/bin/nologin
```

*o cut tambem pode usar a sintaxe e bits*

*Traga a saída dos bytes 1 a 4 no arquivo /etc/passwd.*

```
cut -b 1-4 /etc/passwd
```


#### Comando cmp

O comando `cmp` é usado para comparar dois arquivos byte a byte e relatar as diferenças encontradas entre eles. Se os arquivos forem idênticos, o `cmp` não produzirá nenhuma saída; caso contrário, ele mostrará o deslocamento e o byte onde a primeira diferença ocorre. É útil para verificar se dois arquivos são iguais ou identificar onde as diferenças estão localizadas entre eles.

**Exemplo**:

```shell
$ echo "linha 1" > teste
$ cp teste teste-copia
$ cmp teste teste
$ cmp teste teste-copia 
$ echo linha2 >> teste-copia
$ cmp teste teste-copia
```

1. `echo "linha 1" > teste`: Cria um arquivo chamado "teste" e escreve nele a linha "linha 1".
2. `cp teste teste-copia`: Faz uma cópia do arquivo "teste" chamada "teste-copia".
3. `cmp teste teste`: Compara o arquivo "teste" consigo mesmo. Como são idênticos, não há saída, indicando que os arquivos são iguais.
4. `cmp teste teste-copia`: Compara o arquivo "teste" com sua cópia "teste-copia". Novamente, como são idênticos, não há saída.
5. `echo linha2 >> teste-copia`: Acrescenta a linha "linha2" ao final do arquivo "teste-copia".
6. `cmp teste teste-copia`: Agora, ao comparar os arquivos novamente, o `cmp` detecta que eles são diferentes e relata onde a primeira diferença é encontrada.

Este exemplo demonstra como o `cmp` é usado para verificar se dois arquivos são idênticos ou onde as diferenças estão localizadas entre eles.

| Comando    | Descrição                                                                                      |
|------------|------------------------------------------------------------------------------------------------|
| `cmp -s`   | Retorna apenas um código de saída. Se os arquivos forem iguais, o código de saída será 0; se houver diferenças, será 1. O resultado pode ser verificado na variável `$?`. |


#### Comando diff

O comando `diff` é usado para comparar o conteúdo de dois arquivos linha por linha e mostrar as diferenças entre eles. Ele mostra as linhas que são diferentes e onde essas diferenças ocorrem. O `diff` é frequentemente usado para verificar as alterações feitas em um arquivo em relação a uma versão anterior ou para comparar dois arquivos para sincronização ou verificação de integridade.

**Sintaxe básica**:

```
diff arquivo1 arquivo2
```

| Comando              | Descrição                                                                                                                                                            |
|----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `diff arquivo1 arquivo2` | Compara o conteúdo de `arquivo1` e `arquivo2` linha por linha e mostra as diferenças encontradas.                                                                    |
| `diff -u`            | Mostra a saída com a diferença entre os arquivos de forma mais legível, utilizando um formato unificado.                                                           |
| `diff -r`            | Mostra a diferença entre os conteúdos de diretórios de forma recursiva, comparando todos os arquivos e subdiretórios dentro deles.                                 |

#### Comando path

O comando `patch` é usado para aplicar as diferenças entre dois arquivos, geralmente representadas em um arquivo no formato de patch, a um arquivo original. Isso é comumente usado em colaboração de desenvolvimento, onde uma pessoa faz alterações em um arquivo, gera um patch descrevendo essas alterações e, em seguida, outra pessoa pode aplicar esse patch ao arquivo original para incorporar essas alterações.

Aqui está a explicação do comando que você forneceu:


| Opção | Descrição                                                                                                                                                                                                                                                     |
| ----- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| patch | O próprio comando para aplicar patches.                                                                                                                                                                                                                       |
| `-p1` | Especifica o nível de segmentação a ser removido do caminho do arquivo contido no patch. O número 1 aqui indica que o caminho do arquivo no patch deve ser modificado, removendo o primeiro componente do caminho.                                            |
| `-N`  | Tenta aplicar o patch, mesmo se o arquivo original não existir. Isso é útil quando você está aplicando patches a vários diretórios e nem todos eles contêm todos os arquivos originais. Sem essa opção, o patch falharia se o arquivo original não existisse. |
| `-R`  | Reverte o patch aplicado, desfazendo as alterações feitas pelo patch. Essa opção é útil para restaurar o estado original dos arquivos após a aplicação de um patch.                                                                                           |

`</tmp/diferencas.path`: Especifica o arquivo de patch a ser aplicado. Nesse caso, o patch está sendo fornecido por meio da entrada padrão (`<`), com o arquivo localizado em `/tmp/diferencas.path`.

Em resumo, esse comando aplica as diferenças descritas no arquivo de patch `/tmp/diferencas.path` aos arquivos originais, ajustando os caminhos dos arquivos conforme necessário e ignorando a ausência de arquivos originais.
#### Comando whereis

O comando `whereis` é utilizado para localizar os arquivos binários, fontes e páginas de manual associados a um determinado comando. Ele retorna o caminho dos arquivos relacionados ao comando especificado.

**Exemplo:**
```
whereis ls
```

**Saída:**
```
ls: /usr/bin/ls /usr/share/man/man1/ls.1.gz
```

- `/usr/bin/ls`: Este é o caminho para o executável do comando `ls`.
- `/usr/share/man/man1/ls.1.gz`: Este é o caminho para o arquivo de manual (`man`) do comando `ls`.

Essa saída indica que o comando `ls` está localizado em `/usr/bin/ls` e o arquivo de manual está localizado em `/usr/share/man/man1/ls.1.gz`. Essas informações são úteis para encontrar a localização dos arquivos associados a um comando no sistema.



## Execução de programas

#### Variavel PATH

O "path" é o conjunto de diretórios onde o sistema operacional procura por arquivos executáveis e comandos quando você os digita em um terminal. Este caminho é armazenado na variável de ambiente PATH. Para visualizar o conteúdo desta variável em um terminal no Unix/Linux, você pode usar o comando `echo $PATH`.

Por exemplo, um caminho típico como "/usr/local/bin:/usr/bin:/bin:/usr/bin/X11" indica que quando você digita um comando como "ls", o interpretador de comandos procura pelo programa "ls" primeiro no diretório "/usr/local/bin". Se não encontrar lá, continua procurando nos diretórios subsequentes, como "/usr/bin", "/bin", e assim por diante, até que o arquivo seja encontrado. Esse processo ocorre sequencialmente em cada diretório listado no PATH.

Caso o interpretador de comandos chegue até o último diretório do path e não encontre o arquivo/comando
digitado, é mostrada a seguinte mensagem:

```shell
bash: ls: command not found (comando não encontrado)
```

O caminho de diretórios, conhecido como PATH, é configurado durante a instalação do Linux, mas pode ser modificado no arquivo `/etc/profile`. Se você deseja alterar o PATH para todos os usuários, o arquivo `/etc/profile` é o local mais apropriado, pois é lido por todos os usuários durante o processo de login.

Se um arquivo ou comando não estiver localizado em nenhum dos diretórios listados no PATH, você pode executá-lo usando `./` antes do comando para indicar que ele está no diretório atual.

Para alterar o PATH apenas para um usuário específico, você pode modificar o arquivo `.bash_profile` em seu diretório de usuário (home).

É importante observar que, por motivos de segurança, não é recomendado incluir o diretório atual (`$PWD`) no PATH.


#### Execução em primeiro e segundo plano

Existem duas formas de executar um programa em um sistema:

1. **Primeiro Plano (Foreground)**: Neste modo, você deve esperar que o programa atual termine sua execução antes de poder inserir um novo comando. O terminal permanece ocupado até que o programa seja concluído, e apenas então o aviso de comando é exibido novamente.

2. **Segundo Plano (Background)**: Aqui, você pode iniciar um programa sem precisar esperar que ele termine para inserir novos comandos. Após iniciar um programa em segundo plano, você recebe um número de identificação de processo (PID) e o aviso de comando é novamente mostrado, permitindo o uso normal do sistema. O programa continua sendo executado internamente. Quando terminar, o sistema retorna uma mensagem de pronto, acompanhada do PID do processo concluído.

Para iniciar um programa em primeiro plano, basta digitar seu nome normalmente. Para executá-lo em segundo plano, acrescente o caractere "&" ao final do comando.

É importante observar que, mesmo que um usuário saia do sistema, um programa iniciado em segundo plano continuará sendo executado até ser concluído ou finalizado pelo usuário que o iniciou (ou pelo usuário root).

Exemplo: `find / -name boot.b &`

Neste exemplo, o comando `find` será executado em segundo plano, liberando o sistema para outras tarefas. Após a conclusão do comando `find`, uma mensagem será exibida.

Os comandos podem ser executados em sequência, um após o término do outro, se os separarmos com ";". Por exemplo:

```bash
echo primeiro; echo segundo; echo terceiro
```

Neste caso, os comandos "echo primeiro", "echo segundo" e "echo terceiro" serão executados sequencialmente, um após o término do outro. Cada comando será executado independentemente do resultado dos comandos anteriores.



#### Comando ps

| Opção         | Descrição                                                                                                   |
|---------------|-------------------------------------------------------------------------------------------------------------|
| `a`           | Mostra os processos criados por você e por outros usuários do sistema.                                      |
| `x`           | Mostra processos que não estão associados ao terminal atual.                                                 |
| `u`           | Mostra o nome de usuário que iniciou o processo e a hora em que o processo foi iniciado.                    |
| `m`           | Mostra a quantidade de memória ocupada por cada processo em execução.                                        |
| `f`           | Exibe a árvore de execução de comandos, ou seja, os comandos que são chamados por outros comandos.          |
| `e`           | Exibe as variáveis de ambiente no momento da inicialização do processo.                                      |
| `w`           | Mostra a continuação da linha atual na próxima linha, em vez de cortar o restante que não couber na tela.   |
| `--sort:[coluna]` | Organiza a saída do comando `ps` de acordo com a coluna escolhida (por exemplo, pid, utime, ppid, rss, size, user, priority). Pode ser especificada uma listagem em ordem inversa, adicionando `-` antes da coluna. |

Essas opções podem ser combinadas para fornecer uma listagem mais completa dos processos em execução. O comando `ps` não requer hífen para especificar as opções, pois não utiliza opções longas ou parâmetros.

***Exemplos de uso incluem** `ps`, `ps ax|grep inetd`, `ps auxf`, `ps auxw`.*

#### Comando top
O comando `top` é uma ferramenta poderosa para monitorar o sistema em tempo real, exibindo informações detalhadas sobre os programas em execução, o uso de CPU e memória, disponibilidade de recursos e muito mais.

##### Uso Básico:

| Ação                     | Descrição                                                                                          |
|--------------------------|----------------------------------------------------------------------------------------------------|
| Execução do `top`        | Basta digitar `top` no terminal para iniciar a exibição em tempo real dos processos.              |
| Sair do `top`            | Pressione a tecla `q` para sair do programa.                                                      |

##### Opções do Comando `top`:

| Opção      | Descrição                                                                                                 |
|------------|-----------------------------------------------------------------------------------------------------------|
| `-d [tempo]` | Atualiza a tela após um intervalo de tempo especificado em segundos.                                     |
| `-s`       | Inicia o top no modo seguro.                                                                              |
| `-i`       | Inicia o top ignorando o tempo ocioso de processos zumbis.                                                |
| `-c`       | Mostra a linha de comando ao invés do nome do programa.                                                    |

##### Teclas Úteis:

| Tecla/Ação    | Descrição                                                                                                    |
|---------------|--------------------------------------------------------------------------------------------------------------|
| **Espaço**    | Atualiza imediatamente a tela.                                                                               |
| **CTRL+L**    | Limpa e atualiza a tela.                                                                                     |
| **h**         | Exibe a tela de ajuda do programa, mostrando todas as teclas de atalho disponíveis.                         |
| **i**         | Ignora o tempo ocioso de processos zumbis.                                                                   |
| **q**         | Sai do programa.                                                                                             |
| **k**         | Finaliza um processo semelhante ao comando kill. Você será solicitado a fornecer o número de identificação do processo (PID). Este comando não está disponível quando o top é executado com a opção -s. |
| **n**         | Altera o número de linhas mostradas na tela. Se 0 for especificado, toda a tela será usada para listar os processos. |

#####  Mais Informações:

- **Ajuda do `top`**: Dentro do programa, pressione a tecla `h` para obter ajuda ou consulte a página de manual (man top) para mais detalhes.

O `top` é uma ferramenta valiosa para monitorar e diagnosticar o desempenho do sistema em tempo real, fornecendo uma visão abrangente dos processos em execução e dos recursos do sistema.


### Parando Momentaneamente a Execução de um Processo

Para parar a execução de um processo que está rodando em primeiro plano, basta pressionar as teclas `CTRL+Z`. O programa em execução será pausado e será mostrado o número de seu job e o aviso de comando.

Para retomar a execução de um comando pausado, use os comandos `fg` ou `bg`.

### Comando `jobs`

O comando `jobs` mostra os processos que estão pausados ou rodando em segundo plano. Processos em segundo plano são iniciados usando o símbolo "&" no final da linha de comando ou através do comando `bg`.

### Comandos `fg` e `bg`

- **`fg`**: Permite fazer um programa rodando em segundo plano ou pausado rodar em primeiro plano. Você deve usar o comando `jobs` para obter o número do processo rodando em segundo plano ou pausado, e este número será passado como parâmetro para o comando `fg`.
  - Exemplo: `fg [número]`. Onde `[número]` é o número obtido através do comando `jobs`. Caso seja usado sem parâmetros, o `fg` utilizará o último programa pausado (o maior número obtido com o comando `jobs`).
- **`bg`**: Permite fazer um programa rodando em primeiro plano ou pausado rodar em segundo plano. Para fazer um programa em primeiro plano rodar em segundo, é necessário primeiro interromper a execução do comando.
  Para permitir que um programa em execução em primeiro plano ou pausado seja executado em segundo plano, você precisa primeiro interromper a execução do programa pressionando `CTRL+Z`. Isso irá pausar o programa e mostrar o número da tarefa interrompida.

Para retomar a execução do programa em segundo plano, você pode usar o comando `bg [número]`, onde `[número]` é o número do programa obtido quando você pressionou as teclas `CTRL+Z` ou através do comando `jobs`.

Por exemplo:
```
bg 106
```

Este comando iniciará a execução do programa em segundo plano.

### Finalizando um Processo Pausado

Um processo pausado pode ser finalizado usando o comando `kill %[num]`, onde `[num]` é o número do processo obtido pelo comando `jobs`.

Esses comandos oferecem controle flexível sobre a execução de processos no sistema, permitindo pausar, retomar e gerenciar a execução de programas.



#### Comando pstree

*O comando `pstree` é uma ferramenta de linha de comando em sistemas baseados em Unix e Linux que exibe uma representação hierárquica dos processos em execução no sistema. Ele mostra os processos em forma de árvore, onde cada processo é listado abaixo de seu processo pai, facilitando a visualização da relação entre os processos.*


| Comando           | Descrição                                                                                                         |
|-------------------|-------------------------------------------------------------------------------------------------------------------|
| `pstree`          | Retorna a árvore de processos sendo executados no sistema operacional de forma mais gráfica.                      |
| `pstree -A`       | Retorna a árvore de processos usando caracteres ASCII 2.                                                         |
| `pstree -c`       | Mostra toda a estrutura incluindo os processos pai.                                                              |
| `pstree -h`       | Mostra os processos pai e os ancestrais.                                                                         |
| `pstree -p`       | Retorna mostrando o PID dos processos.                                                                          |
| `pstree -H 352`   | Retorna em destaque o processo após receber o PID 352.                                                          |
| `pstree -u`       | Retorna o UID do processo.                                                                                       |
| `pstree -g`       | Mostra o grupo de execução dos processos.                                                                        |

##### Comando kill/kilall

Aqui está a informação melhorada e organizada em tabela Markdown:

##### Comando `kill`

| Opção      | Descrição                                                                                                     |
|------------|---------------------------------------------------------------------------------------------------------------|
| `[número]` | Número de identificação do processo obtido com o comando `ps`. Também pode ser o número após o sinal de % obtido pelo comando `jobs` para matar uma tarefa interrompida. |
| `[sinal]`  | Sinal que será enviado ao processo. Se omitido, usa -15 como padrão.                                           |
| `-9`       | Envia um sinal de destruição ao processo ou programa. Ele é terminado imediatamente sem chances de salvar os dados ou apagar os arquivos temporários criados por ele.          |

##### Comando `killall`

| Opção      | Descrição                                                                                                   |
|------------|-------------------------------------------------------------------------------------------------------------|
| `[processo]` | Nome do processo que deseja finalizar.                                                                     |
| `[sinal]`  | Sinal que será enviado ao processo (pode ser obtido usando a opção -l).                                     |
| `-i`       | Pede confirmação sobre a finalização do processo.                                                           |
| `-l`       | Lista o nome de todos os sinais conhecidos.                                                                 |
| `-q`       | Ignora a existência do processo.                                                                            |
| `-v`       | Retorna se o sinal foi enviado com sucesso ao processo.                                                     |
| `-w`       | Finaliza a execução do killall somente após finalizar todos os processos.                                   |

##### Comando `killall5`

| Sintaxe        | Descrição                                                    |
|----------------|--------------------------------------------------------------|
| `killall5 [sinal]` | Envia um sinal de finalização para todos os processos em execução.   |

##### Sinais do Sistema

| Sinal | Valor       | Ação | Comentário                                                    |
|-------|-------------|------|---------------------------------------------------------------|
| HUP   | 1           | A    | Travamento detectado no terminal de controle ou finalização do processo controlado. |
| INT   | 2           | A    | Interrupção através do teclado.                                |
| QUIT  | 3           | C    | Sair através do teclado.                                      |
| ILL   | 4           | C    | Instrução Ilegal.                                             |
| ABRT  | 6           | C    | Sinal de abortar enviado pela função abort.                   |
| FPE   | 8           | C    | Exceção de ponto Flutuante.                                   |
| KILL  | 9           | AEF  | Sinal de destruição do processo.                              |
| SEGV  | 11          | C    | Referência Inválida de memória.                               |
| PIPE  | 13          | A    | Pipe Quebrado: escreveu para o pipe sem leitores.             |
| ALRM  | 14          | A    | Sinal do Temporizador da chamada do sistema alarm.            |
| TERM  | 15          | A    | Sinal de Término.                                             |
| USR1  | 30,10,16   | A    | Sinal definido pelo usuário 1.                                |
| USR2  | 31,12,17   | A    | Sinal definido pelo usuário 2.                                |
| CHLD  | 20,17,18   | B    | Processo filho parado ou terminado.                           |
| CONT  | 19,18,25   | -    | Continuar a execução, se interrompido.                        |
| STOP  | 17,19,23   | DEF  | Interromper processo.                                         |
| TSTP  | 18,20,24   | D    | Interromper digitação no terminal.                            |
| TTIN  | 21,21,26   | D    | Entrada do terminal para o processo em segundo plano.          |
| TTOU  | 22,22,27   | D    | Saída do terminal para o processo em segundo plano.           |

